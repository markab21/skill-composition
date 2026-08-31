# Project Placement for Skills

This file gives the rules for where skills live in a project
repository, and how the agent loads them.

## The Two Locations

| Location | Holds | Tracked in git |
|---|---|---|
| `skills/<name>/` | Skills that the project owns | Yes |
| `.agents/skills/<name>/` | The load path of the agent | No |

`skills/` is the source of truth for project-owned skills. The load
path, for example `.agents/skills/`, is a local install target. Add
the load path to `.gitignore`.

## The Decision Test

Ask one question: "Did this project write the skill?"

- Yes. The skill lives in `skills/<name>/`.
- No. The skill was installed from another repository. It lives in
  the load path only.

## Project-Owned Skills

1. Put the skill folder in `skills/<name>/`.
2. Link the folder into the load path:
   `ln -s ../../skills/<name> .agents/skills/<name>`.
3. Edit the skill only in `skills/`. The link gives the agent the
   current text.
4. If a script in the skill uses a path, write the path against
   `skills/<name>/`, not against the load path.

## Vendored Skills

A vendored skill comes from another repository, for example through
`npx skills add <owner>/<repo>`.

1. Install it into the load path only.
2. Do not track it in git.
3. Do not edit it. If it has a defect, report the defect upstream, or
   fork the source repository.
4. Record its name and its source in AGENTS.md. A new machine then
   installs the same set again.

## AGENTS.md Policy

Record the skill policy in the AGENTS.md of the project. The policy
must state:

- Project-owned skills live in `skills/` and are tracked.
- Vendored skills live in the load path and stay out of git.
- The install command for each vendored skill.
- The link step for each project-owned skill.

Example policy text:

> Project-owned skills live in `skills/`. Edit them there. Vendored
> skills install into `.agents/skills/` with `npx skills add` and
> stay out of git. To load a project skill locally, link it:
> `ln -s ../../skills/<name> .agents/skills/<name>`.

## Moving a Misplaced Skill

If a project-owned skill sits in the load path as a real folder:

1. Move the folder to `skills/<name>/`. If git tracks it, move it
   with `git mv`.
2. Create the link in the load path.
3. Search the repository for the old path. Update each reference:
   `grep -rn ".agents/skills/<name>" .`
4. Add the load path to `.gitignore`. If git tracks vendored files,
   remove them from the index: `git rm -r --cached .agents/skills`.
5. Make sure that the agent still finds the skill. List the load
   path and read the link target.

Do these moves in one commit that touches only skill files. Do not
mix a placement move with content edits.
