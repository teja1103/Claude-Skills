# Evaluation ladder

Match rigor to stakes. Higher levels cost more time and tokens.

---

## L0 — Smoke (minutes)

**When:** First draft, or trivial scope.

- 1–2 **realistic** user prompts (full context, not “do the thing”).
- Run with skill available; skim for gross misunderstandings.
- No baseline required.

**Exit:** Obvious gaps fixed before deeper investment.

---

## L1 — Human review (subjective skills)

**When:** Writing style, UX copy, visual design, strategy narratives.

- Small rubric (3–7 criteria, 1–5 scale) or freeform feedback per prompt.
- **No** automated pass/fail pretense—avoid misleading metrics.

**Exit:** Stakeholder sign-off on representative prompts.

---

## L2 — Benchmark (objective / mixed)

**When:** Verifiable outputs, regressions, “did we improve?”

### Conventions

- Workspace as sibling to skill: `<skill-name>-workspace/iteration-N/`.
- Per eval: descriptive **directory names**, not only `eval-0`.
- **Parallelize:** Spawn with-skill and baseline runs **in the same batch** when subagents exist.
  - New skill baseline: **no skill**.
  - Improve skill baseline: **prior skill snapshot** (copy before edit).

### Assertions

- Name assertions for **discrimination**—they should fail when the task is botched.
- Prefer checks tied to **content**, not filenames alone.
- Programmatic checks > eyeball when repeatable.

### Artifacts

- `eval_metadata.json` per eval (prompt, assertions).
- `timing.json` when the environment exposes token/time notifications—capture on completion; they may not persist elsewhere.
- `grading.json`: use `expectations[]` with `text`, `passed`, `evidence` (viewer-compatible field names).

### Aggregate

- If your environment includes the reference **skill-creator** scripts, run `aggregate_benchmark` and `generate_review.py` per that bundle’s docs ([references/integration.md](references/integration.md)).
- Otherwise: summarize pass rates and deltas in markdown from the same data.

### Analyzer pass

- Flag **non-discriminating** assertions (always pass).
- Flag **high variance** evals (flaky or unstable).
- Note **time/token** tradeoffs.

---

## L3 — Blind compare (high uncertainty)

**When:** Two skill versions both “look fine”; need impartial preference.

- Comparator sees outputs **A/B without labels** mapping to versions.
- After verdict, run **post-hoc analysis**: map winner/loser to skill files and transcripts; extract **causal** instruction differences—not vibes.

Use [subagent-briefs.md](subagent-briefs.md) for comparator and analyzer shapes.

---

## When NOT to escalate

- User explicitly wants a lightweight helper.
- Task is purely subjective and metrics would lie.
- Environment lacks parallel execution—run sequentially; downgrade L2 expectations accordingly.
