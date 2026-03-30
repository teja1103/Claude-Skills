# Installing skills from this repository

Skills ship as directories under `skills/<skill-name>/`. Install them by making that directory available to your agent client.

## Cursor

**Project-only (recommended for teams)**  
Copy or symlink the skill into the project:

```bash
mkdir -p .cursor/skills
ln -s /absolute/path/to/claude-skills/skills/market-analyzer .cursor/skills/market-analyzer
```

**User-wide**  
Put the skill under the user skills folder (exact path can vary by Cursor version):

```bash
mkdir -p ~/.cursor/skills
ln -s /absolute/path/to/claude-skills/skills/market-analyzer ~/.cursor/skills/market-analyzer
```

Restart the editor or start a new agent chat so discovery picks up the skill.

## Claude Code / Claude Desktop

Product-specific skill locations change over time. Use the official documentation for the product you use, and point it at a folder that contains one subdirectory per skill, each with a `SKILL.md` at the root of that subdirectory.

This repo’s layout matches the usual pattern: one folder per skill, `SKILL.md` inside the folder.

## Verifying

Open `skills/<name>/SKILL.md` and confirm:

- YAML frontmatter includes `name` and `description`.
- The description states what the skill does and when to use it.

If the client lists available skills, your new skill should appear after installation and refresh.
