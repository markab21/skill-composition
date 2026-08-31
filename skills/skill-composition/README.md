# skill-composition

A skill that teaches an agent how to write, review, and score other
skills.

## What This Skill Is

A skill is a folder with a SKILL.md file and optional support files.
This skill gives the agent:

- A six-step process to write a skill.
- Fifteen rubrics (R1-R15) to score a skill. See
  `references/rubrics.md`.
- The folder layout and file limits. See `references/file-structure.md`.
- The rules for reference files. See `references/reference-files.md`.
- The placement rules for project and vendored skills. See
  `references/placement.md`.

The structural rules come from the Skills Directory documents "Writing
Effective Skills", "Skill File Structure", and "Using Reference Files".

## Layout

```
skills/skill-composition/
├── SKILL.md
├── README.md
└── references/
    ├── rubrics.md
    ├── file-structure.md
    ├── reference-files.md
    └── placement.md
```

## How to Use It

1. Install the skill in your agent, or paste SKILL.md into the context.
2. Ask the agent to write a skill, review a skill, or score a skill.
3. The agent applies the six steps and reports the rubric scores.

## How to Test It

Test the skill with a small model. A small model shows unclear
instructions first.

1. Give the model the SKILL.md text and one authoring task.
2. Score the output against `references/rubrics.md`.
3. If the output breaks a rubric, make the related instruction more
   specific. Then test again.
