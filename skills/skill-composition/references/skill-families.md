# Rules for Skill Families

This file gives the rules for a family of skills: two or more sibling
skills that divide one domain, for example one CLI or one product area.

## When a Family Is Correct

A split into siblings is correct when each sibling passes rubric R1 on
its own. A split is too fine when a sibling has no step that differs
from another sibling. Merge such siblings.

## The Router Skill

When a family has three or more siblings, write one router skill:

1. Give the router the plain domain name, for example `acme-cli`. Give
   each sibling a suffixed name, for example `acme-cli-auth`.
2. Put a selection table in the router: one row for each task area, one
   sibling for each row.
3. Put the steps that every sibling needs in the router, one time. For
   example: login checks, target confirmation, and safety boundaries.
4. In each sibling, point back to the router for those shared steps. Do
   not copy the shared steps into the siblings.

## Disjoint Triggers

The agent matches descriptions, not the router table. Two siblings with
one shared trigger word both start on one task.

- Give each trigger word to one sibling only.
- Put the broad domain words in the router description only.
- After you write the family, list every trigger word in one table.
  If a word appears in two rows, move it or remove it.

## One Wording for a Shared Step

When a step must appear in more than one sibling, write it one time and
copy it exactly. "Confirm the Company with `auth status`" and "Run
`auth status` and confirm the Company" are one step with two wordings.
Two wordings read as two different rules.

## No Empty Skills

Every skill folder must hold a SKILL.md file. Do not commit scaffold
folders without content. An empty folder in the skills tree reads as a
skill and pollutes discovery.

## Family Checklist

Check the family after each change:

- [ ] Each sibling passes R1 alone.
- [ ] A router exists when the family has three or more siblings.
- [ ] The router table names every sibling one time.
- [ ] No trigger word appears in two sibling descriptions.
- [ ] Each shared step has one exact wording in every place it appears.
- [ ] No skill folder lacks a SKILL.md file.
- [ ] All siblings use one name for each domain object.
