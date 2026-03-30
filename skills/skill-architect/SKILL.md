---
name: skill-architect
description: >-
  Designs, authors, refines, and evaluates Agent Skills (SKILL.md skills) using structured intent capture, trigger craft, token-aware layout, and staged evaluation. Use when the user wants to create a new skill from scratch, upgrade or merge skills, fix under/over-triggering, run disciplined evals (bench, blind compare), or optimize descriptions—especially when they want a rigorous approach beyond informal instructions. Also use for skill architecture reviews and when the user mentions skill-creator, meta-skills, or skill quality.
---

# Skill Architect

Build **high-leverage skills**: clear triggers, lean context, verifiable outcomes where it matters, and a repeatable path from draft to shipped skill.

This skill subsumes informal “skill creator” workflows but optimizes for **decisions first**, **progressive disclosure**, and **staged evaluation** so you do not burn tokens or time on the wrong rigor level.

## Principles (read once, apply always)

1. **Description is the product** — Discovery runs on `name` + `description` only. Put “what + when + strong negatives” in the description; do not hide triggers in the body.
2. **Classify before writing** — See [design-framework.md](design-framework.md). Deterministic skills deserve assertions; subjective skills deserve rubrics and human review.
3. **Progressive disclosure** — Metadata → SKILL.md → bundled files. Keep SKILL.md under ~500 lines; push depth to one-hop references.
4. **Explain why, avoid ritual MUSTs** — Prefer reasoning the model can generalize over all-caps rules that invite gaming.
5. **Generalize from evals** — Feedback on a few prompts is a proxy for infinite prompts; avoid overfitting those examples.

---

## Where the user is

| Situation | Start here |
|-----------|------------|
| Empty canvas (“make a skill for X”) | Phase A: Design contract → draft SKILL.md |
| Existing draft | Phase B: Classify → gap analysis → edit |
| Wrong triggers (misses or false positives) | [trigger-and-description.md](trigger-and-description.md) |
| “Is it better?” / regression risk | [evaluation-ladder.md](evaluation-ladder.md) L2–L3 |
| Packaging / JSON schemas / viewer pipeline | [references/integration.md](references/integration.md) |

Stay flexible: if the user wants a fast draft without evals, comply—still capture intent in a short design contract so later hardening is cheap.

---

## Phase A — From intent to first draft

### 1. Harvest context

From chat history (if any), extract: tools used, step order, corrections, output shapes. Fill gaps with targeted questions.

### 2. Fill the design contract

Use the template in [design-framework.md](design-framework.md). Minimum: **job-to-be-done**, **must-trigger phrases**, **must-not-trigger**, **outputs**, **verification mode** (objective / subjective / mixed).

### 3. Write SKILL.md

- **Frontmatter**: `name` (kebab-case, ≤64 chars), `description` (third person, WHAT + WHEN + near-miss negatives; see trigger craft).
- **Body**: Imperative instructions, templates, workflows. Link out for long reference tables.
- **Bundling**: `scripts/` for deterministic repetition; `references/` for heavy docs; `assets/` for static templates. See layout in [design-framework.md](design-framework.md).

### 4. Preflight

Run the **ship checklist** in [design-framework.md](design-framework.md) before calling anything “done.”

---

## Phase B — Evaluate and iterate (staged)

Do **not** jump to full benchmark + blind compare for every skill. Pick a level:

| Level | Fit | Actions |
|-------|-----|---------|
| **L0** | Early draft | 1–2 realistic prompts, inline review |
| **L1** | Most subjective / creative skills | Human rubric + structured feedback |
| **L2** | Objective or mixed skills | Assertions, with-skill vs baseline, aggregate stats |
| **L3** | Version battle or high stakes | Blind A/B + post-hoc analysis |

Full staging criteria, folder conventions, and parallel-run rules are in [evaluation-ladder.md](evaluation-ladder.md).

**Grader / comparator / analyzer** — When you spawn specialized subagents, give them the condensed briefs in [subagent-briefs.md](subagent-briefs.md). For field-exact JSON schemas (grading, benchmark, comparison), use the same structures as the reference **skill-creator** bundle if present ([references/integration.md](references/integration.md)).

---

## Phase C — Improve the skill from evidence

1. **Generalize** — Turn specific fixes into durable rules or scripts; avoid per-eval hacks.
2. **Delete** — Remove instructions that burned tokens without improving outcomes (check transcripts).
3. **Deduplicate** — If every run reinvented the same script, add `scripts/` once and point the skill to it.
4. **Re-check triggers** — After substantive body edits, revisit description coverage ([trigger-and-description.md](trigger-and-description.md)).

---

## Description optimization (without requiring automation)

Automation (train/test splits, repeated trigger probes) is optional; see [references/integration.md](references/integration.md).

**Manual path (always available):**

1. Draft **10–20 probe queries**: half should invoke the skill, half should not—**near-miss negatives** beat irrelevant negatives.
2. For each probe, predict trigger/no-trigger; reconcile misses by tightening **wording in the description** (synonyms, tasks, domains, exclusions).
3. Keep probes **substantive** — trivial one-step tasks may never consult a skill regardless of wording.

Full patterns and anti-patterns: [trigger-and-description.md](trigger-and-description.md).

---

## Communication

Match the user’s technical comfort. Briefly define terms like “assertion,” “baseline,” or “held-out” when context does not show expertise. Offer depth in stages—framework first, machinery second.

---

## Product-specific notes

- **No subagents / no browser** — Use L0/L1; present outputs in chat; skip blind benchmark requirements.
- **Headless / static HTML** — Prefer static review artifacts over servers when specified in integration docs.
- **Claude Code / Cowork** — Full ladder available; parallel runs when stable.

---

## Additional resources

| File | Purpose |
|------|---------|
| [design-framework.md](design-framework.md) | Design contract, layouts, ship checklist |
| [evaluation-ladder.md](evaluation-ladder.md) | L0–L3 rigor, workspaces, grader fields |
| [trigger-and-description.md](trigger-and-description.md) | Trigger matrix, probe sets, under/over-trigger |
| [subagent-briefs.md](subagent-briefs.md) | Grader, comparator, analyzer prompts |
| [references/integration.md](references/integration.md) | Optional skill-creator scripts & schemas |

---

## Core loop (summary)

Capture intent → classify skill type → draft with lean SKILL.md and rich description → stage-appropriate evals → generalize improvements → re-check triggers → ship.
