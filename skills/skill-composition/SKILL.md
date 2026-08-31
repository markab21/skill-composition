---
name: skill-composition
description: >-
  Write, review, and score agent skills (SKILL.md packages). Use when you
  create a skill, improve a skill, review a skill, score a skill against
  rubrics, split a large skill, write a skill description, or add reference
  files. Covers skill scope, descriptions, file structure, progressive
  disclosure, rubrics, and smoke tests.
---

# Skill Composition

This skill tells you how to write an effective agent skill. A skill is a
folder with a SKILL.md file and optional support files. The rules come from
the Skills Directory documentation and from ASD-STE100 Simplified Technical
English (STE).

## When to Use This Skill

Use this skill when you:

- Create a skill.
- Review or score a skill.
- Split a skill that has more than one job.
- Add reference files to a skill.

Do not use this skill for prose that is not a skill. For general technical
prose, use an STE writing skill.

## Language Rules

Write all skill text in STE:

- Write each instruction in the imperative: "Run the test."
- Write a maximum of 20 words in each instruction sentence.
- Write a maximum of 25 words in each description sentence.
- Put each condition before its command: "If the test fails, read the log."
- Use one word for one meaning in the whole skill.
- Use only these modal verbs: can, will, must.
- Do not use: should, would, may, might, could.
- Do not use contractions or semicolons.
- Write "the section that follows", not "the section below" or "above".
- Write "for example", not "such as", "e.g.", or "etc.".

Models read "should" as optional. Write "must" for each requirement.
Code, commands, identifiers, and quoted text are exact names. Do not change
them. Each one counts as one word.

## Step-by-Step Process

### Step 1: Define one job

Write one sentence: "This skill does X." If the sentence needs "and", split
the work into two skills. One skill does one job.

### Step 2: Write the description

The agent finds a skill through a semantic match with its description.
Write the words that users say when they need the skill.

The description must contain:

- What the skill does, in one sentence.
- When to use the skill, as "Use when ...".
- The trigger words of the domain, for example tool names and task names.

### Step 3: Write the SKILL.md body

Use this structure, in this sequence:

1. "When to Use This Skill" — the trigger conditions, positive and negative.
2. "Step-by-Step Process" — the numbered steps.
3. "Output Format" — the structure of the response.
4. "Avoid" — the actions that are not permitted.
5. "Examples" — one input and one output, as a minimum.

Write specific instructions with limits and names. Write "Functions must
have fewer than 50 lines", not "write clean code". Name the stack, the
tools, and the file paths. Do not assume that the model knows them.

Add a checklist for each task where the model must not miss items.
Give each special case an explicit rule. Example: "If the file has fewer
than 20 lines, do not give refactor suggestions."

### Step 4: Add reference files

If SKILL.md has more than 500 lines, move content into `references/`.
Obey these limits:

- Keep SKILL.md under 500 lines.
- Keep each reference file under 200 lines.
- Give each reference file one topic and a clear name.
- Start each reference file with one sentence about its content.
- Point to each file from SKILL.md: "For X, see `references/x.md`."

### Step 5: Score the skill

Score the draft against the rubrics in `references/rubrics.md`. Each
criterion gets 0, 1, or 2 points. If a criterion scores less than 2,
correct the skill. Then score the skill again.

### Step 6: Do a smoke test

Do this step only when the user gives a test command or a test model.
If no test command is available, deliver the skill with the rubric
scores and stop.

Test the skill with a small model. A small model shows the unclear
instructions first. Do each test one time, in sequence. Do not start
parallel test agents. Do these tests:

1. Give the model the skill text and one task in scope.
2. Make sure that the output obeys the structure and the limits of the skill.
3. Give the model one task out of scope.
4. Make sure that the model does not apply the skill to that task.
5. Give the model a task that mixes two jobs.
6. Make sure that the model splits the work or reports the extra job.

If a test fails, find the instruction that the model did not obey. Make
that instruction more specific. Then do the test again.

## Output Format

When you write a skill, deliver these items, in this sequence:

1. The skill text, or the skill folder with SKILL.md and support files.
2. The rubric scores, one line for each criterion.
3. The smoke test results, one line for each test, when Step 6 ran.

Deliver the full response in one message. Do not stop at an interim
status. Write the report in the same language rules as the skill.

When you review a skill, report each problem as: rubric ID, the text with
the problem, a corrected version.

## Avoid

- Do not put more than one job in one skill.
- Do not write vague instructions, for example "write good code".
- Do not write two instructions that give opposite commands.
- Do not put a requirement in a note. Put each requirement in a step.
- Do not copy full documents into SKILL.md. Use a reference file.
- Do not nest one list in another list.
- Do not invent facts, numbers, or tool names to look precise.

## Example

### Input

"Write a description for a skill that makes unit tests for React
components."

### Output

> Creates unit tests for React components with Jest and React Testing
> Library. Use when you test React components, write test cases, or
> configure component tests. Triggers: "test this component", "add tests",
> "Jest", "React Testing Library".

### Why

The description names the tools, gives "Use when" conditions, and lists
trigger words. A vague form ("Helps with testing stuff") gives the agent
no words to match.

## References

- `references/rubrics.md` — the scoring rubrics for skill quality.
- `references/file-structure.md` — the folder layout, file limits, and names.
- `references/reference-files.md` — the rules for reference files.
