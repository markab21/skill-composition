# Project Skill Audit

This file gives the procedure for a full audit of the skills in a
project. The audit reads and reports. It changes nothing. Corrections
come after the audit, in separate commits, with the user's answer.

## When to Run an Audit

- After an agent has authored several skills.
- Before you add a skill family.
- When skills start on the wrong tasks.
- When the skills tree looks disorganized.

## Step 1: Inventory

1. List every folder in `skills/` and in the load path.
2. For each folder, record: the name, the SKILL.md line count, the
   reference file count, tracked or untracked, and link or real folder.
3. Report each folder that has no SKILL.md file.

Example commands:

```bash
for f in skills/*/SKILL.md; do wc -l "$f"; done
git ls-files skills | cut -d/ -f2 | sort | uniq -c
ls -la .agents/skills/
```

## Step 2: Classify placement

Apply the decision test from `placement.md` to each folder:

1. Mark each skill as project-owned or vendored.
2. Make sure that git tracks each project-owned skill in `skills/`.
3. Make sure that git does not track the load path.
4. Make sure that a link connects each project-owned skill into the
   load path.
5. Score R14 for each skill.

## Step 3: Score each project-owned skill

1. Score each skill against R1 to R13 and R15 in `rubrics.md`.
2. Report each problem as: rubric ID, the text with the problem, a
   corrected version.
3. Do not score the content of a vendored skill. If a vendored skill
   has a defect, report the upstream source instead.
4. If a vendored copy is stale, report the update command.

## Step 4: Check each family

1. Group sibling skills by domain.
2. Collect every description. Build one table: trigger word, skill.
3. Report each trigger word that appears in two rows.
4. Run the family checklist in `skill-families.md`.
5. Find shared steps with different wording:
   `grep -h "<step text>" skills/*/SKILL.md | sort | uniq -c`
6. Score R16 for each family.

## Step 5: Report

Deliver one report with:

1. The inventory table: skill, lines, references, placement, score,
   pass or fail.
2. The problem list: rubric ID, skill, the text with the problem, a
   corrected version.
3. The correction plan, in this priority: placement breaks first,
   trigger collisions second, the lowest rubric scores third.

Stop after the report. Apply corrections only after the user answers.
Put placement moves and content edits in separate commits.
