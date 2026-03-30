# Integration with skill-creator tooling

**Skill Architect** is instruction-first: it defines *how* to design and stage work. The **skill-creator** skill (external bundle) ships Python scripts, HTML assets, and eval viewers that automate parts of L2–L3 and description optimization.

If you have that bundle on disk (for example `skill-creator/` with `scripts/`, `eval-viewer/`, `assets/`):

| Capability | Typical entrypoint | Notes |
|------------|-------------------|--------|
| Validate frontmatter | `python -m scripts.quick_validate <skill-path>` | Requires Python + PyYAML |
| Aggregate benchmark | `python -m scripts.aggregate_benchmark <workspace>/iteration-N --skill-name <name>` | Produces `benchmark.json` / `benchmark.md` |
| Human review UI | `eval-viewer/generate_review.py` | Use `--static <path>` when no browser server |
| Description optimization loop | `python -m scripts.run_loop --eval-set … --skill-path …` | May invoke `claude -p`; environment-dependent |
| Package `.skill` | `python -m scripts.package_skill <skill-folder>` | When `present_files` or packaging is available |

**Schemas** for `evals.json`, `grading.json`, `benchmark.json`, `comparison.json`, `analysis.json` live in that bundle’s `references/schemas.md`. Match field names exactly—viewers are brittle.

**Without the bundle:** Use L0/L1 manually; for L2, still produce the same **logical** artifacts (prompts, assertions, pass/fail, notes) in markdown or JSON you control.

**Security:** Only run bundled scripts from sources you trust.
