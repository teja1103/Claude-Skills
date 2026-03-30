# Subagent briefs

Condensed instructions when spawning **grader**, **blind comparator**, or **post-hoc analyzer** roles. For full JSON field inventories, use the **skill-creator** bundle’s `references/schemas.md` if available.

---

## Grader

**Input:** Expectations (strings), transcript path, outputs directory.

**Process:**

1. Read transcript end-to-end; list output files.
2. For each expectation, search **both** transcript and **artifact contents**—do not pass on filename alone if content matters.
3. Verdict: **pass** only with substantive evidence; **fail** if missing, contradicted, or superficially satisfied.
4. Extract extra **claims** from outputs; verify where possible.
5. **Critique evals** when warranted: non-discriminating assertions, missing coverage—document under `eval_feedback`.

**Output:** `grading.json` with `expectations[]` items `{ "text", "passed", "evidence" }`, plus `summary`, optional `claims`, `eval_feedback`. Match field names expected by your viewer tooling.

**Bias:** Burden of proof to pass; prefer false negatives in eval design discussion over false confidence.

---

## Blind comparator

**Input:** Labeled outputs A and B only (no skill identities), eval prompt, optional expectations.

**Process:**

1. Derive a **task-specific rubric** (content + structure dimensions; 1–5 per cell).
2. Score A and B independently; compute overall 1–10 style summary per side.
3. If expectations exist, count pass rates as **secondary** evidence.
4. Choose winner **A**, **B**, or **TIE** (rare); justify with concrete deltas.

**Output:** `comparison.json` with `winner`, `reasoning`, `rubric`, `output_quality`; include `expectation_results` only if expectations were provided.

**Bias:** Judge deliverables, not author—no guessing which skill produced which.

---

## Post-hoc analyzer (after blind compare)

**Input:** Winner id, paths to both skills and transcripts, comparator JSON.

**Process:**

1. Unblind: map A/B to concrete skill versions.
2. Diff **instructions** and **bundled tools**—what could explain the outcome?
3. Score **instruction following** per transcript (1–10) with specific misses.
4. Emit **prioritized** improvements: `instructions`, `tools`, `examples`, `error_handling`, `structure`, `references`.

**Output:** `analysis.json` with `winner_strengths`, `loser_weaknesses`, `improvement_suggestions[]` (priority: high/medium/low), `transcript_insights`.

**Bias:** Causal links only—do not blame the agent for ambiguous skill text.

---

## Benchmark note author

**Input:** `benchmark.json` or equivalent aggregates.

**Process:** Emit short notes: non-discriminating assertions, per-eval variance, token/time outliers, surprising cross-eval patterns. **Do not** propose skill edits here—that is a separate improvement step.

**Output:** JSON array of strings or `notes` field per schema in reference bundle.
