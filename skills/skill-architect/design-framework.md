# Design framework

## Skill types (pick one primary)

| Type | Verification | Skill body emphasizes |
|------|--------------|------------------------|
| **Deterministic** | Scripts, file diffs, structured checks | Exact steps, scripts, validation commands |
| **Judgment-heavy** | Rubrics, human review | Criteria, examples, failure modes |
| **Hybrid** | Mix of checks + review | Separate “objective” and “quality” sections |

Choosing the wrong type produces either brittle MUSTs or fake precision.

---

## Design contract (fill before writing SKILL.md)

```markdown
## Skill: <name>

### Job-to-be-done
One sentence: what does the agent accomplish when this skill applies?

### Trigger signals
- Must invoke when: (bullets — user phrasings, domains, file types)
- Must NOT invoke when: (bullets — adjacent tools, competing intents)

### Inputs / outputs
- Typical inputs:
- Expected outputs (format):

### Constraints
- Tools or libraries to prefer or avoid:
- Security / policy lines:

### Verification mode
- [ ] Objective (machine-checkable)
- [ ] Subjective (human or rubric)
- Notes:

### Success in one test
Describe one end-to-end prompt that proves the skill works.
```

---

## Repository layout

```
skill-name/
├── SKILL.md           # Frontmatter + instructions (keep concise)
├── scripts/           # Deterministic helpers (optional)
├── references/        # Long docs, API dumps (optional)
├── assets/            # Templates, HTML shells (optional)
└── evals/             # evals.json — if using formal evals (optional)
```

**Domain splits** — For multi-cloud / multi-stack skills, use `references/aws.md`, `references/gcp.md`, etc., and a short router section in SKILL.md.

---

## Progressive disclosure tiers

1. **Metadata** (~100–150 words in description) — Always eligible for injection; must carry trigger burden.
2. **SKILL.md body** — Loaded when skill triggers; target <500 lines.
3. **Bundled files** — Read or execute on demand; can be large.

**Rule:** If a section is rarely needed, move it to `references/` and link once.

---

## Ship checklist

Before shipping:

- [ ] `name` matches directory; kebab-case; ≤64 chars.
- [ ] `description` is third person; includes WHAT, WHEN, and at least one **non-obvious exclusion** if confusion is likely.
- [ ] No secrets, malware, or misleading intent.
- [ ] Instructions are imperative; examples are concrete.
- [ ] Long content is not pasted twice—single source of truth + link.
- [ ] For objective skills: at least one discriminating check (not “file exists” alone).
- [ ] Subjective skills: rubric or review path documented—no fake assertions.

---

## Anti-patterns

- **Kitchen-sink skills** — Split when triggers diverge.
- **Body-only triggers** — Triggers belong in description.
- **All-caps MUST chains** — Replace with rationale where possible.
- **Duplicated scripts in prose** — Promote repeated code to `scripts/`.
