# AI engineering practices and patterns

Deep reference for the ai-engineer skill. Organized by engineering surface area.

---

## Data engineering for ML

### Data quality is model quality

The single highest-leverage activity in most ML projects is improving data, not model architecture. Before adding complexity, ask: "Is my data clean, representative, and correctly labeled?"

### Pipeline design

- **Idempotent transforms**: every pipeline step produces the same output for the same input. No hidden state, no append-only bugs.
- **Schema enforcement**: validate data at ingestion, after every transform, and before model consumption. Catch type drift, null spikes, and distribution shifts early.
- **Versioning**: hash datasets or tag with commit + timestamp. A model is only reproducible if you can reconstruct the exact data it trained on.
- **Lineage**: track which raw sources produced which processed datasets. When a data bug surfaces, you need to trace it backward.

### Labeling and annotation

- Define labeling guidelines with edge cases and ambiguous examples resolved upfront. Inter-annotator agreement is a metric, not a formality.
- Use programmatic labeling (weak supervision, heuristics, LLM-assisted labeling) for scale, but always validate against a human-labeled gold set.
- Track label quality over time — annotator fatigue and guideline drift are real.

### Train/val/test discipline

| Split | Purpose | Rules |
|-------|---------|-------|
| **Train** | Model learns from this | Largest partition |
| **Validation** | Hyperparameter and architecture decisions | Never leak into training; use for early stopping |
| **Test** | Final evaluation only | Touch once per release; never tune against it |

- For time-series or sequential data: temporal splits only. Random splits create leakage.
- For user-level data: split by user, not by example — otherwise the model memorizes users.
- For small datasets: cross-validation with held-out final test.

---

## Training and fine-tuning

### Classical ML

- Start with simple models (logistic regression, gradient-boosted trees) and strong feature engineering. They're fast to iterate, easy to debug, and often competitive.
- Feature importance analysis is cheap — run it before building complex pipelines.
- Calibration matters for risk-sensitive applications (medical, financial). Accuracy alone is insufficient.

### Deep learning

- **Learning rate** is the most important hyperparameter. Use learning rate finders or well-established schedules (cosine with warmup).
- **Overfit a single batch first** — if the model can't memorize a tiny dataset, the architecture or code has bugs.
- **Gradient monitoring**: watch for NaN/Inf, exploding gradients, or vanishing gradients. Log gradient norms.
- **Checkpointing**: save every N steps, not just at epoch boundaries. Verify checkpoint restore before launching long runs.

### Foundation model fine-tuning

- **Full fine-tune vs parameter-efficient (LoRA, QLoRA, adapters)**: LoRA is the default for cost/quality tradeoff. Full fine-tune when you have enough data and compute, and LoRA quality is insufficient.
- **Data quality over quantity**: 1,000 excellent examples often beats 100,000 noisy ones for instruction-tuning.
- **Catastrophic forgetting**: evaluate on a held-out general-capability set alongside your task-specific metrics.
- **Training format**: match the inference-time format exactly. If the model will see system prompts, tool schemas, or multi-turn context at inference, it should see them during training.

### Hyperparameter search

- Random search beats grid search in most settings (Bergstra & Bengio 2012 — still true).
- Bayesian optimization (Optuna, Ray Tune) for expensive runs where each trial costs real money.
- Track the full config for every run. "I think I used lr=3e-4" is not reproducibility.

---

## Evaluation and benchmarking

### Eval design principles

1. **Evals are the spec**: if you can't write an eval for it, you can't claim it works.
2. **Multiple metrics**: a single number hides tradeoffs. Report accuracy/F1 AND latency AND cost AND failure rate.
3. **Failure-case analysis**: aggregate metrics hide important patterns. Slice by category, input length, difficulty, demographics.
4. **Eval maintenance**: production bugs become test cases. The eval suite grows monotonically.

### Eval types by system layer

| Layer | What to measure | Tools |
|-------|----------------|-------|
| **Data** | Schema validity, distribution stats, freshness | Great Expectations, custom validators |
| **Model** | Accuracy, calibration, fairness, robustness | Task-specific metrics, held-out test sets |
| **Retrieval** | Recall@k, precision@k, MRR, latency | BEIR, MTEB, custom query-doc pairs |
| **Generation** | Correctness, safety, format compliance, hallucination rate | LLM-as-judge, human eval, regex/schema checks |
| **System** | End-to-end task completion, latency p50/p95/p99, cost | Integration test suites, load tests |

### LLM-as-judge

- Define explicit rubrics with score anchors (what does a 1 vs 5 look like?).
- Validate judge agreement against human ratings on a calibration set before trusting it at scale.
- Watch for position bias (LLMs prefer the first option), verbosity bias (longer = higher rated), and self-preference (GPT-4 rates GPT-4 outputs higher).
- Use pairwise comparison (A vs B) rather than absolute scoring when possible — humans and LLMs are better at relative judgments.

---

## Inference and serving

### Serving patterns

| Pattern | When to use |
|---------|-------------|
| **Real-time API** | User-facing, latency-sensitive (<500ms) |
| **Batch inference** | Periodic bulk processing, cost-sensitive |
| **Streaming** | Token-by-token LLM output, long-generation tasks |
| **Edge/on-device** | Privacy, offline, ultra-low latency |

### LLM serving

- **KV cache management** is the bottleneck for throughput. Use paged attention (vLLM, TensorRT-LLM) or continuous batching.
- **Speculative decoding** for latency reduction on long generations.
- **Prompt caching**: cache common system prompts and prefixes to avoid recomputation.
- **Request routing**: different models for different complexity levels (small model for easy queries, large for hard ones).

### Optimization stack

| Level | Techniques |
|-------|------------|
| **Algorithm** | Distillation, pruning, architecture search |
| **Precision** | FP16, BF16, INT8, INT4 (quantization) — always validate quality after |
| **Compilation** | torch.compile, TensorRT, ONNX Runtime, XLA |
| **Batching** | Dynamic batching, continuous batching for LLMs |
| **Caching** | Semantic cache for similar queries, KV cache reuse, prompt prefix caching |
| **Infrastructure** | Right-size GPU/instance, spot instances for batch, autoscaling policies |

### Cost engineering

- Track cost per request and cost per useful output (not just raw inference cost).
- Cache aggressively: semantic similarity cache for LLM calls can cut costs 30-60% for repetitive workloads.
- Cascade: try a cheap/small model first, escalate to expensive model only when confidence is low.
- Batch where latency allows — throughput per dollar is much higher than real-time serving.

---

## MLOps and production

### Monitoring

| Signal | What to watch |
|--------|--------------|
| **Input drift** | Feature distributions shifting from training baseline |
| **Output drift** | Prediction distributions, confidence calibration changing |
| **Performance** | Latency p50/p95/p99, throughput, error rates |
| **Quality** | Online metrics (click-through, user corrections, escalations) |
| **Cost** | $/request, $/day, GPU utilization |

### Deployment patterns

- **Shadow mode**: run new model alongside old, compare outputs, don't serve new outputs to users yet.
- **Canary**: route small % of traffic to new model; automated rollback on metric degradation.
- **Blue/green**: full cutover with instant rollback capability.
- **Feature flags**: toggle model versions, prompt versions, or retrieval configs without deployment.

### Incident response for ML

ML incidents are different from software incidents:
- **Silent failures**: the model returns a response, but it's wrong. No 500 error to alert on.
- **Slow degradation**: quality decays over weeks as data drifts. No single moment of failure.
- **Root cause ambiguity**: is it the data, the model, the prompt, the retrieval, or the preprocessing?

Build monitoring that catches silent failures: output distribution monitoring, automated spot-checks against golden examples, user feedback loops.

### Reproducibility checklist

- [ ] Code: exact commit hash
- [ ] Data: version hash or snapshot ID
- [ ] Environment: container image or full dependency lockfile + CUDA/driver versions
- [ ] Config: all hyperparameters, prompt templates, and feature flags
- [ ] Random seeds: fixed where applicable
- [ ] Hardware: GPU type, count, distributed strategy (results can differ across hardware)

---

## Security and safety

### API key and credential management

- Rotate model provider API keys on schedule. Leaked keys drain budgets fast.
- Per-environment keys (dev/staging/prod). Never share production keys with development.
- Rate limiting on your own API to prevent abuse and cost explosion.

### Prompt injection and adversarial inputs

- Assume user input will attempt prompt injection. Separate system instructions from user content structurally (not just with delimiters).
- Output validation: check that model outputs conform to expected formats before acting on them.
- Guardrails: content filtering on both input and output for safety-critical applications.
- Audit logging: record inputs and outputs for post-hoc analysis of abuse patterns.

### Data privacy

- PII handling: scrub training data; anonymize or pseudonymize before model training.
- Model memorization: test whether the model can regurgitate training examples.
- Retention policies: define how long inference logs (which may contain user data) are kept.

---

## Technology landscape (decision points, not endorsements)

| Decision | Options and tradeoffs |
|----------|----------------------|
| **Training framework** | PyTorch (ecosystem, flexibility) · JAX (functional, XLA) · TF (legacy, production tooling) |
| **LLM serving** | vLLM (throughput) · TGI (HuggingFace ecosystem) · TensorRT-LLM (NVIDIA optimization) · Ollama (local dev) |
| **Experiment tracking** | W&B (features, cost) · MLflow (open source, self-hosted) · simple git + CSV (small teams) |
| **Orchestration** | Kubeflow / Airflow (batch) · Ray (distributed compute) · Modal / Replicate (serverless GPU) |
| **Vector stores** | pgvector (Postgres ecosystem) · Pinecone (managed) · Weaviate / Qdrant / Milvus (feature-rich) |
| **Eval frameworks** | Custom scripts (most flexible) · promptfoo · Braintrust · LangSmith |
| **LLM frameworks** | Direct API calls (simplest) · LangChain (ecosystem) · LlamaIndex (retrieval focus) · Instructor (structured output) |

The right choice depends on team size, existing infrastructure, and operational maturity. Defaults: start simple, add infrastructure when pain demands it.
