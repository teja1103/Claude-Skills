# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## What this repo is
This repository is an **Agent Skill** implemented entirely as Markdown.

The "runtime" artifact is `SKILL.md`: the agent reads the YAML frontmatter (metadata) and the prompt/instructions that follow.

## Key files (and how they relate)
- `SKILL.md`
  - The actual skill definition.
  - YAML frontmatter (`---` … `---`) with `name`, `version`, `description`.
  - Three-pass humanization method: Strip AI patterns → Inject human signals → Audit against detectors.
- `patterns.md`
  - Reference file with detailed before/after examples for all 24 general AI writing patterns.
  - Read by the agent when it needs detailed examples; not loaded by default.
- `academic.md`
  - Reference file with detailed before/after examples for all 12 academic-specific AI patterns (A1–A12).
  - Read by the agent when humanizing research papers, dissertations, or academic essays.
- `README.md`
  - Installation and usage instructions.
  - Summarized pattern tables and version history.

When changing behavior/content, treat `SKILL.md` as the source of truth, and update `README.md` and `patterns.md` to stay consistent.

## Common commands
### Install the skill into Cursor
```bash
mkdir -p ~/.cursor/skills
git clone https://github.com/blader/humanizer.git ~/.cursor/skills/humanizer
```

## How to "run" it
Invoke the skill: `/humanizer` then paste text.

## Making changes safely
### Versioning (keep in sync)
- `SKILL.md` has a `version:` field in its YAML frontmatter.
- `README.md` has a "Version History" section.

If you bump the version, update both.

### Editing `SKILL.md`
- Preserve valid YAML frontmatter formatting and indentation.
- Keep pattern numbering stable (README and patterns.md reference the same numbers).
- SKILL.md should stay under 500 lines. Move detailed examples to patterns.md.

### Documenting non-obvious fixes
If you change the prompt to handle a tricky failure mode, add a short note to `README.md`'s version history describing what was fixed and why.
