# Rules for Reference Files

This file gives the rules for the `references/` folder of a skill.
Source: Skills Directory, "Using Reference Files".

## Why Reference Files

- The agent loads a reference file only when the task needs it. This
  keeps the context small.
- SKILL.md stays focused. Detail and edge cases live in separate files.
- You can update one topic without an edit of the whole skill.

## Rules

1. Give each reference file one topic.
2. Keep each reference file under 200 lines. If a file grows, split it
   by subtopic.
3. Name each file for its content: `react-hooks.md`, not `advanced.md`
   or `part2.md`.
4. Start each file with one sentence about its content and its parent
   skill.
5. Point to each file from SKILL.md: "For X, see `references/x.md`."

## Pointer Forms

Use the inline form when the agent must read the file on demand:

> For query optimization, see `references/database.md`.

Use the block form when the agent must read the file before the task:

> Before you continue, read `references/examples.md`. Apply those
> patterns to the current task.

## Large Collections

If a skill has many reference files, group them in subfolders by
category. Add an `index.md` that lists each file with one line of
content. Do not nest subfolders more than two levels.

## Common Reference File Types

- Examples collection: numbered examples with input and output.
- Troubleshooting guide: symptom, then solution, for each problem.
- Checklist file: one checklist for each repeated task.

## Test the Pointers

After you write a skill, make sure that the agent reads the reference
files when the task needs them. If the agent does not read a file, make
the pointer a block form instruction.
