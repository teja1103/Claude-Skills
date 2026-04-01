# Research methodology reference

Deep reference for the ai-researcher skill. Covers experimental design, statistical methods, paper structure, and review criteria.

---

## Experimental design

### Variables and controls

Every experiment has:
- **Independent variable(s)**: what you're changing (model architecture, hyperparameter, training data, method component).
- **Dependent variable(s)**: what you're measuring (accuracy, latency, perplexity, human preference).
- **Controlled variables**: everything else, held constant. If it's not controlled, it's a confounder.

**The gold standard**: change exactly one thing and measure the effect. When that's too expensive (common in ML), be explicit about what you're conflating and why.

### Ablation design

| Type | Structure | When to use |
|------|-----------|-------------|
| **Subtractive** | Full system → remove one component → measure drop | Default for "does each part contribute?" |
| **Additive** | Simplest baseline → add one component → measure gain | Default for "what's the minimum viable method?" |
| **Factorial** | All combinations of K binary factors (2^K runs) | When interactions between components matter; expensive |
| **One-at-a-time** | Vary one factor, fix others at default | Cheap, misses interactions, but acceptable for expensive experiments |

For K > 4 factors: fractional factorial designs or Latin hypercube sampling reduce runs while preserving coverage.

### Compute budgets and fair comparison

Comparing methods at different compute budgets is comparing apples to oranges. Options:
1. **Fixed compute**: same GPU-hours or FLOPs for all methods. Report what each method achieves within budget.
2. **Fixed quality**: same target metric. Report compute required to reach it.
3. **Pareto frontier**: plot quality vs compute for each method. The dominating method is the one with better quality at every compute level.

Always report: GPU type, count, training time, total FLOPs where feasible.

### Hyperparameter search fairness

- Same search budget (number of trials) for all methods being compared.
- Same search strategy (random, Bayesian, grid) unless the search strategy itself is the contribution.
- Report the search space for each method, not just the best config found.

---

## Statistical methods for ML experiments

### Variance and confidence

**Why it matters**: neural networks are sensitive to random seeds, data ordering, and initialization. A single run is an anecdote.

**Minimum practice**: 3-5 runs with different random seeds. Report mean ± standard deviation.

**Better**: bootstrap confidence intervals. Resample your test-set predictions 1000+ times, compute the metric on each resample, report the 95% interval. Works for any metric, no distributional assumptions.

### Hypothesis testing

| Scenario | Recommended test |
|----------|-----------------|
| Two systems, one metric, paired samples | Paired bootstrap test or Wilcoxon signed-rank |
| Two systems, one metric, independent samples | Permutation test or Mann-Whitney U |
| Multiple systems | Friedman test + Nemenyi post-hoc, or permutation-based alternatives |
| Comparing to a fixed threshold | One-sample test against threshold |

**Practical notes:**
- p-values alone are insufficient. Always report effect size (difference in means, Cohen's d, or the metric itself).
- With large test sets, tiny meaningless differences become "statistically significant." Practical significance matters.
- For multiple comparisons: Holm-Bonferroni correction is strictly more powerful than Bonferroni and just as easy.

### When to use what

- **Paired bootstrap**: most ML settings where you have predictions from two systems on the same test set. Robust, few assumptions.
- **McNemar's test**: binary correct/incorrect per example, two systems. Simple and effective.
- **Permutation tests**: general-purpose, exact (no distribution assumptions), slightly more expensive computationally.

### Bayesian alternatives

When you care about "how much better" rather than "is it significantly better":
- Bayesian estimation (BEST) gives posterior distributions over effect size.
- Credible intervals are more interpretable than confidence intervals for most practitioners.
- Region of Practical Equivalence (ROPE): define a range of differences you'd consider negligible, then report the probability that the true difference falls inside/outside ROPE.

---

## Paper structure and writing

### Standard ML paper sections

| Section | Purpose | Common mistakes |
|---------|---------|-----------------|
| **Abstract** | Self-contained summary: problem, method, result, implication | Too vague; no numbers; hides limitations |
| **Introduction** | Motivate the problem, state contribution, preview results | Overselling; not positioning against prior work |
| **Related work** | Map the landscape, identify the gap your work fills | Citation dump without synthesis; missing key work |
| **Method** | Precise enough to reimplement; assumptions stated | Unclear notation; hiding details in appendix |
| **Experiments** | Fair evaluation, ablations, analysis | Weak baselines; no error bars; cherry-picked examples |
| **Results/Discussion** | Interpret findings, acknowledge limitations | Ignoring where the method fails; over-claiming |
| **Conclusion** | Summary + honest future directions | "Exciting future work" without specifics |

### Writing quality signals

**Clarity over cleverness:**
- Define notation once, early, and consistently.
- One idea per paragraph. Topic sentence states the point; rest supports it.
- Active voice by default. "We train the model" not "The model was trained."

**Precision:**
- "Our method outperforms X" — by how much, on what, with what statistical confidence?
- "We use a large dataset" — how large? What's in it?
- "Recent work has shown" — which work? Citation needed.

**Honest framing:**
- State limitations in the paper, not just in the appendix. Reviewers notice avoidance.
- Distinguish between "we haven't tested this" and "we tested this and it doesn't work."
- If a result is preliminary, say so. Overclaiming destroys credibility.

### Figures and tables

- Every figure should be interpretable without reading the body text. Captions carry weight.
- Axis labels, units, legends — always. Meaningful axis ranges (don't start accuracy axes at 90% to exaggerate small differences, unless you also show the full range somewhere).
- Error bars or shaded regions for uncertainty. State what they represent (std dev, 95% CI, etc.) in the caption.
- Tables: bold the best result, but also indicate statistical significance. "Best" without significance testing is a coin flip.

---

## Reviewing and critique

### Structured review framework

When reviewing (others' work or your own):

1. **Summary**: one paragraph restating what the paper claims and how.
2. **Strengths**: what's genuinely good — novel contribution, solid evaluation, clear writing.
3. **Weaknesses**: organized by severity.
   - **Fatal**: undermines the core claim (data leakage, unfair baselines, incorrect math).
   - **Major**: significantly weakens the contribution (missing ablation, insufficient evaluation, unclear method).
   - **Minor**: could be improved but doesn't undermine claims (writing clarity, additional experiments, presentation).
4. **Questions**: things you're uncertain about that could change your assessment.
5. **Recommendation**: accept/reject/revise with clear justification tied to specific strengths and weaknesses.

### Red flags in ML papers

- Test-set accuracy reported without variance, number of runs, or confidence intervals.
- Baselines from 2+ years ago without re-running them on current data/hardware.
- "Our method achieves state-of-the-art" but only on one metric, one dataset, one split.
- Ablation table where removing any component helps — suggests the full model is overfit to the ablation.
- Compute cost never mentioned.
- No qualitative error analysis or failure examples.
- Code/data "available upon request" (often means "never").

### Constructive feedback patterns

- "The comparison on dataset X would be stronger if baseline Y were included, because..."
- "Table 3 would benefit from confidence intervals — without them it's unclear whether the 0.3% improvement is noise."
- "The method section assumes familiarity with [X]; a brief definition in Section 3.1 would help accessibility."
- "This is an interesting direction. The core concern is whether the evaluation in Section 5 supports the claim in the abstract, specifically..."

---

## Reproducibility

### NeurIPS/ICML reproducibility checklist (condensed)

- [ ] Clear description of the algorithm, sufficient for reimplementation
- [ ] All hyperparameters specified, including search procedure
- [ ] Exact training and evaluation data described (or provided)
- [ ] Compute resources reported (GPU type, count, hours)
- [ ] Random seeds reported and used for multiple runs
- [ ] Error bars or confidence intervals on all main results
- [ ] Code availability (link, license)
- [ ] Negative results or failure cases reported

### What "reproducible" means in practice

Three levels:
1. **Repeatable**: same code, same data, same hardware → same numbers (±floating point). Seeds, deterministic mode.
2. **Reproducible**: different implementation from the paper description → similar numbers. Requires clear method description.
3. **Replicable**: different team, different data from same distribution → similar conclusions. The strongest test.

Most papers should target level 1 (code release) and level 2 (clear writing). Level 3 is the field's job over time.

---

## Benchmark and dataset design

### When existing benchmarks are insufficient

Signs you need a new benchmark or evaluation protocol:
- Existing benchmarks are saturated (near-perfect scores, improvements within noise).
- The task you care about isn't covered by existing benchmarks.
- Existing benchmarks have known contamination issues with foundation models.
- The evaluation metric doesn't match what users actually care about.

### Benchmark design principles

- **Diverse and representative**: cover the distribution of real use cases, not just easy cases.
- **Discriminating**: hard enough that random/trivial baselines score low, but not so hard that everything scores zero.
- **Unambiguous**: clear labeling guidelines with high inter-annotator agreement.
- **Versioned**: with contamination detection (canary strings, held-out splits, time-based cuts).
- **Documented**: datasheet or data card describing collection, demographics, known biases, intended use.

### Contamination awareness

Foundation models may have seen benchmark data during pretraining. Mitigation:
- Check for memorization (exact-match probing of test examples).
- Use time-based splits (test data from after the model's training cutoff).
- Create private held-out sets that are never publicly released.
- Report contamination analysis alongside results.
