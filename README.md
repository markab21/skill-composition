# skill-composition

A skill that teaches an agent how to write, review, and score other
agent skills.

## What This Repository Holds

The skill lives in `skills/skill-composition/`. It contains:

- `SKILL.md` — the six-step process to write a skill.
- `references/rubrics.md` — fourteen rubrics (R1-R14) that score a
  skill, with pass lines and an N/A rule.
- `references/file-structure.md` — the folder layout, the file limits,
  and the naming rules.
- `references/reference-files.md` — the rules for reference files.
- `references/placement.md` — where skills live in a project: owned
  skills in `skills/`, vendored skills in the untracked load path.
- `README.md` — the usage notes for the skill itself.

## What the Skill Does

An agent with this skill can:

- Write a new skill with one job, a searchable description, and
  specific instructions.
- Review an existing skill and report each problem with a rubric ID,
  the text with the problem, and a corrected version.
- Score a skill against the rubrics and give a pass or fail result.
- Split a skill that mixes more than one job.
- Organize the skills of a project: owned skills in `skills/`, vendored
  skills in the untracked load path, and a policy in AGENTS.md.

## Why You Use It

Skills fail for known causes. A skill with two jobs does neither job
well. A vague description never triggers. A vague instruction gives
different output on each run. The rubrics in this skill catch each of
these causes before you ship the skill.

The skill also sets language rules for the skills it writes: short
sentences, imperative steps, one word for one meaning, and no optional
modals. Models read "should" as optional. These rules write "must".
This makes the instructions hard to misread, for models and for people.

The structural rules come from the Skills Directory documents "Writing
Effective Skills", "Skill File Structure", and "Using Reference Files".

## How to Install It

Install with the skills CLI:

```
npx skills add markab21/skill-composition
```

Or copy `skills/skill-composition/` into the skills folder of your
agent.

## License

MIT. See the `LICENSE` file.
