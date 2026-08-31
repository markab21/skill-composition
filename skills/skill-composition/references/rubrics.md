# Rubrics for Skill Quality

This file gives the scoring rubrics for a skill. Score each criterion with
0, 1, or 2 points. The sources are the Skills Directory documents "Writing
Effective Skills" (WES), "Skill File Structure" (SFS), and "Using Reference
Files" (URF).

## How to Score

A score of 2 means full obedience. A score of 1 means partial
obedience. A score of 0 means no obedience.

If the review material does not show the item of a criterion, write
"N/A". Remove its 2 points from the maximum. Do not give points for
absent material.

A skill passes when the total is 80% or more of the applicable maximum,
and no criterion in R1, R2, or R3 has a score of 0. Correct the lowest
scores first.

## The Rubrics

### R1 — One job

The skill has one clear purpose. The purpose fits in one sentence without
"and". Source: WES, "One Skill = One Job".

- 2: One job. The name states the job.
- 1: One primary job with small unrelated additions.
- 0: The skill mixes two or more jobs.

### R2 — Description as search query

The description contains what the skill does, "Use when" conditions, and
the trigger words that users say. Source: WES, "Write Descriptions Like
Search Queries".

- 2: All three parts are present with specific words.
- 1: One part is missing or the words are generic.
- 0: The description is vague, for example "Helps with testing stuff".

### R3 — Specific instructions

The instructions give limits, numbers, and names, not general advice.
Source: WES, "Be Specific, Not Vague".

- 2: Each instruction is testable. Limits have numbers. Tools have names.
- 1: Some instructions are testable. Some are general advice.
- 0: The instructions are general advice, for example "write clean code".

### R4 — Clear hierarchy

The body has this sequence: when to use, steps, output format, avoid,
examples. Steps are numbered. Source: WES, "Use Clear Hierarchies".

- 2: All five sections are present and in sequence.
- 1: One section is missing.
- 0: The body is unstructured prose.

### R5 — Checklists and edge cases

The skill gives checklists for thorough tasks and rules for special cases.
Source: WES, "Include Checklists" and "Define Edge Cases".

- 2: Checklists are present. Special cases have explicit rules.
- 1: One of the two is present.
- 0: Neither is present.

### R6 — Anti-patterns

The skill has an "Avoid" section with the actions that are not permitted.
Source: WES, "Tell Claude What NOT to Do".

- 2: The section is present with specific prohibitions.
- 1: The section is present but generic.
- 0: The section is absent.

### R7 — Examples

The skill gives at least one full example with input, output, and the
reason. Source: WES, "Include Examples".

- 2: An example with input, output, and reason is present.
- 1: An example is present without the reason.
- 0: No example is present.

### R8 — Progressive disclosure

SKILL.md is under 500 lines. Each reference file is under 200 lines.
Detail lives in `references/`. Source: WES, "Use Progressive Disclosure".
SFS, "File Size Guidelines".

- 2: All limits are obeyed. SKILL.md points to each reference file.
- 1: One file breaks a limit, or a reference file has no pointer.
- 0: SKILL.md holds all content and is over 500 lines.

### R9 — No contradictions

No two instructions give opposite commands. Source: WES, "Common
Mistakes", item 3.

- 2: No contradictions.
- 1: One soft contradiction, for example an unresolved exception.
- 0: Two instructions give opposite commands.

### R10 — Named context

The skill names the stack, the tools, and the formats. It does not assume
knowledge. Source: WES, "Common Mistakes", item 4.

- 2: All tools and formats have names and versions where necessary.
- 1: Some names are present, some are "the standard pattern".
- 0: The skill assumes an unnamed stack.

### R11 — Names and layout

The folder name is lowercase with hyphens. SKILL.md is uppercase.
Reference files are lowercase with hyphens. Source: SFS, "Naming
Conventions".

- 2: All names obey the conventions.
- 1: One name breaks a convention.
- 0: The layout does not follow the structure of SFS.

### R12 — Reference file discipline

Each reference file has one topic, a content sentence at the top, and a
pointer from SKILL.md. Source: URF, "Best Practices".

- 2: All reference files obey all three rules.
- 1: One file breaks one rule.
- 0: Reference files mix topics or have no pointers.

### R13 — Language rules

The skill text obeys the "Language Rules" section of the parent skill:
imperative steps, 20/25-word sentence limits, one word for one meaning,
only can/will/must as modals. Source: SKILL.md, "Language Rules".

- 2: The text obeys all listed language rules.
- 1: The text breaks one to three rules.
- 0: The text breaks more than three rules.

### R14 — Project placement

The skill lives in the correct location for its origin. A project-owned
skill lives in `skills/` and is tracked. A vendored skill lives in the
untracked load path. Source: `placement.md` in this folder.

- 2: Correct location, correct tracking, and the load-path link exists.
- 1: Correct location, but the tracking or the link is wrong.
- 0: A project-owned skill exists only in the untracked load path, or
  git tracks a vendored skill.

### R15 — Alignment before action

A procedural skill reads its inputs before it acts, stops on a missing
or conflicting input, and gates each action that the agent cannot
reverse. Source: SKILL.md, "Alignment Before Action".

- 2: The first step reads the inputs. A gap stops the skill with a
  report. An action that the agent cannot reverse waits for the user.
  Each loop has a stop condition.
- 1: The read step exists, but a gap rule, a gate, or a stop condition
  is missing.
- 0: The skill acts before it reads, or it guesses missing values.

For a descriptive skill with no actions, write "N/A".

### R16 — Family coherence

When sibling skills divide one domain, the family obeys the rules in
`skill-families.md`: a router with a selection table, disjoint trigger
words, one exact wording for each shared step, and no skill folder
without a SKILL.md file. For a standalone skill, write "N/A". Source:
`skill-families.md` in this folder.

- 2: The family obeys all four rules.
- 1: One rule breaks, for example one shared trigger word.
- 0: Two or more rules break, or two siblings claim the same task.

## Score Sheet Template

| Rubric | Score (0-2) | Note |
|---|---|---|
| R1 One job | | |
| R2 Description | | |
| R3 Specificity | | |
| R4 Hierarchy | | |
| R5 Checklists and edge cases | | |
| R6 Anti-patterns | | |
| R7 Examples | | |
| R8 Progressive disclosure | | |
| R9 No contradictions | | |
| R10 Named context | | |
| R11 Names and layout | | |
| R12 Reference files | | |
| R13 Language rules | | |
| R14 Project placement | | |
| R15 Alignment before action | | |
| R16 Family coherence | | |

Maximum: 32 points, minus 2 for each N/A criterion. Pass: 80% or more
of the applicable maximum, with no 0 in R1, R2, or R3.
