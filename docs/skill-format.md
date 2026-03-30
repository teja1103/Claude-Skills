# Skill format

Skills in this repository follow the common **SKILL.md** pattern used by Cursor and similar agents.

## Directory

```
skills/<skill-name>/
├── SKILL.md              # Required
├── <optional>.md         # Optional: referenced from SKILL.md
└── scripts/              # Optional: helper scripts
```

Use **lowercase** names with **hyphens** (for example `market-analyzer`).

## SKILL.md frontmatter

Required keys:

| Key | Purpose |
|-----|---------|
| `name` | Identifier; lowercase letters, numbers, hyphens; max 64 characters. |
| `description` | What the skill does and **when** the agent should use it. Written in third person. Max 1024 characters. |

Example:

```yaml
---
name: example-skill
description: Does X and Y. Use when the user asks for Z or mentions keywords A, B.
---
```

## Body

The markdown body should be **concise**: instructions the model does not already know, workflows, templates, and links to longer material in sibling files (progressive disclosure).

Keep the main file roughly under **500 lines**; move deep reference content to `reference.md`, `templates.md`, or similar, and link from `SKILL.md`.

## References

Link one level deep from `SKILL.md` (for example `[sources.md](sources.md)`), not chains of nested docs.
