# Claude skills

This repository collects **Agent Skills** for Claude and compatible clients (for example Cursor). Each skill is a folder with a `SKILL.md` file (YAML frontmatter plus instructions) and optional supporting markdown files.

## Repository layout

```
claude-skills/
├── README.md                 # This file
├── docs/                     # How to install and contribute skills
└── skills/
    └── <skill-name>/
        ├── SKILL.md          # Required: name, description, instructions
        └── …                 # Optional: templates, references, scripts
```

Skills in `skills/` are the **source of truth**. Copy or symlink them into a client-specific skills directory when you want the agent to load them automatically.

## Available skills

| Skill | Description |
|-------|-------------|
| [market-analyzer](skills/market-analyzer/SKILL.md) | Market sizing, competitive landscape, trends, SWOT, segmentation, with web research and citations. |
| [skill-architect](skills/skill-architect/SKILL.md) | Design, author, refine, and evaluate Agent Skills with intent contracts, trigger craft, staged evals (L0–L3), and optional integration with skill-creator tooling. |
| [project-manager](skills/project-manager/SKILL.md) | From a problem statement: PRD, TRD, Design Document, timeline, and traceable features list. |
| [frontend-developer](skills/frontend-developer/SKILL.md) | UI implementation and review: accessibility, performance, components, modern web practices. |
| [backend-developer](skills/backend-developer/SKILL.md) | APIs, domain logic, data, messaging, security, observability, resilience. |
| [software-architect](skills/software-architect/SKILL.md) | System design, ADRs, quality attributes, tradeoffs, evolution and team-aligned boundaries. |
| [ai-engineer](skills/ai-engineer/SKILL.md) | Build and ship ML/AI systems: data pipelines, training and fine-tuning, evaluation, inference and serving, optimization, MLOps, and debugging—implementation and operations, not literature-only work. |
| [ai-researcher](skills/ai-researcher/SKILL.md) | Research-side AI: literature synthesis, hypotheses, experimental design, ablations, statistical reasoning, reproducibility planning, and clear methods/limitations—papers and rigor, not primary production deployment. |

See each skill’s `SKILL.md` for scope, triggers, and workflows.

**AI engineering vs research:** Use **ai-engineer** when the task centers on code, pipelines, training, deployment, or SLAs. Use **ai-researcher** when the task centers on surveying work, designing experiments, or writing research narratives. Pair them when a project needs both.

## Quick start

1. Clone or copy this repository.
2. Install skills using the paths in [docs/installation.md](docs/installation.md) for your editor or Claude product.
3. In a new task, ask for work that matches the skill’s description (for example “market analysis for electric vehicle charging in Europe”).

For conventions (naming, `SKILL.md` format, optional files), read [docs/skill-format.md](docs/skill-format.md).

## Contributing

To add or change a skill, follow [docs/contributing.md](docs/contributing.md).

## License

Add a `LICENSE` file at the repository root if you plan to publish this repo publicly.
