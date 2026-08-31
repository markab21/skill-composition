# Skill File Structure

This file gives the folder layout, the file limits, and the naming rules
for a skill. Source: Skills Directory, "Skill File Structure".

## Minimum Structure

A skill is a folder with one SKILL.md file:

```
my-skill/
└── SKILL.md
```

## Full Structure

```
my-skill/
├── SKILL.md              # Required: the main instructions
├── references/           # Optional: documentation loaded on demand
├── scripts/              # Optional: executable code
├── templates/            # Optional: file templates
└── assets/               # Optional: static files
```

## Purpose of Each Folder

- `SKILL.md` holds the YAML frontmatter (name, description) and the
  instructions.
- `references/` holds detail documents. The agent loads them only when
  SKILL.md points to them.
- `scripts/` holds code that the agent can run, for example generators
  and validators. Scripts need execute permissions.
- `templates/` holds file templates with markers, for example
  `{{ComponentName}}`.
- `assets/` holds static files, for example images and JSON data.

## File Limits

| File type | Maximum size |
|---|---|
| SKILL.md | 500 lines |
| Reference file | 200 lines |
| Script | 300 lines |
| Template | 100 lines |

Larger files decrease the available context of the agent.

## Naming Rules

- Write folder names in lowercase with hyphens: `code-review/`.
- Write `SKILL.md` in uppercase.
- Write reference files in lowercase with hyphens: `api-guide.md`.
- Give each template the target extension: `component.tsx.template`.

## Loading Behavior

The agent loads a skill in stages:

| Content | When the agent loads it |
|---|---|
| name and description | Always, for skill discovery |
| SKILL.md body | When the skill triggers |
| Reference files | When SKILL.md points to them and the task needs them |
| Scripts | When the task asks for execution |

Because of this behavior, many installed skills stay cheap. Only the
descriptions use permanent context.
