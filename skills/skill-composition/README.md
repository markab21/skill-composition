# skill-composition

A skill that teaches an agent how to write, review, and score other
skills.

## What This Skill Is

A skill is a folder with a SKILL.md file and optional support files.
This skill gives the agent:

- A six-step process to write a skill.
- Thirteen rubrics (R1-R13) to score a skill. See
  `references/rubrics.md`.
- The folder layout and file limits. See `references/file-structure.md`.
- The rules for reference files. See `references/reference-files.md`.

The content comes from the Skills Directory documents "Writing Effective
Skills", "Skill File Structure", and "Using Reference Files". The
language rules come from ASD-STE100 Simplified Technical English (STE).
All text in this skill obeys STE.

## Layout

```
skills/skill-composition/
├── SKILL.md
├── README.md
└── references/
    ├── rubrics.md
    ├── file-structure.md
    └── reference-files.md
```

## How to Use It

1. Install the skill in your agent, or paste SKILL.md into the context.
2. Ask the agent to write a skill, review a skill, or score a skill.
3. The agent applies the six steps and reports the rubric scores.

## How to Test It

Test the skill with a small model. A small model shows unclear
instructions first. This project uses the `dsh` command:

```
dsh --profile headless "<SKILL.md text> Task: <an authoring task>"
```

Score the output against `references/rubrics.md`. If the output breaks a
rubric, make the related instruction more specific. Then test again.
