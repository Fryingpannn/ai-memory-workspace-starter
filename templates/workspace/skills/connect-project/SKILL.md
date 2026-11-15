---
name: connect-project
description: Register a new or existing repository in the outer workspace and connect its agents to shared memory. Use when creating, importing, registering, or connecting a project, or repairing its workspace connection.
---

# Connect Project

Make a repository discoverable from the outer workspace, and make shared memory
reachable from that project's working tree. Use the available filesystem and Git
tools. Repeating this procedure updates missing or stale details without duplicating
profiles or instruction blocks.

This is the reusable connection procedure for an established workspace. Do not rerun
workspace setup or delete a setup clone as a side effect of connecting a project.

## Read the Local Conventions

This file lives at `skills/connect-project/SKILL.md`. The outer workspace is two
directories above it. Read that root's `AGENTS.md`, `projects/README.md`,
`projects/index.md`, and `projects/project-template.md`. Consult `USER.md` when
preferences or approval boundaries matter. Relative paths below start at the outer
root unless stated otherwise. Follow the target project's local instructions too.

## Locate and Inspect

- Inspect the outer Git root, initialization state, remote, branch, and status.
  Identify immediate child repositories, including `.git` files used by worktrees
  and submodules.
- Resolve the repository path and purpose from the request. New repositories
  normally live at `<outer-root>/<repo-name>/`. `projects/` holds metadata only.
- Existing repositories stay in place. For a project outside the outer workspace,
  use the gitignored `projects/local-paths.md` mapping described in
  `projects/README.md`.
- Reuse an existing registry entry or profile and its stable project id. Do not
  create a second profile for the same repository.
- Read the target's root instructions and relevant documentation. Inspect its Git
  root, status, remotes, and remote default branch. Do not guess the remote
  default branch from the current branch. Distinguish an independent repository
  or worktree from a directory merely covered by the parent's Git repository.
- Do not read secrets, credentials, or broad source trees.

## Choose the Git Connection

When the target is or will be an immediate child repository, present one explicit
choice before changing Git integration:

1. **Independent and ignored.** The outer repository ignores the child directory.
   Cloning the outer workspace does not fetch the child. Simplest for beginners.
2. **Git submodule.** The outer repository records the child's remote URL and an
   exact commit. The relationship is portable. The child is checked out separately
   and needs access to its own remote.

Recommend independent and ignored for beginners. Do not silently select or convert
to submodules. Preserve an established connection mode unless a change is requested.
An existing `.git` directory alone does not establish the intended mode.

Honor a connection choice the user has already approved. Otherwise obtain the
choice before changing Git integration.

For a new project, apply the same choice before initialization and registration. A
new submodule needs its own repository, a commit, and a usable remote. Create and
publish those only within the approved scope. If a prerequisite is missing, record
the intended mode as pending. An external repository stays where it is. Connecting
it does not authorize moving it.

## Preserve Repository Boundaries

Never use the public setup repository as the outer workspace remote.

For an independent child repository, show the exact missing root-anchored ignore
entries and obtain approval unless that edit is already authorized. Add them to the
outer `.gitignore` before staging outer metadata. Preserve existing ignore rules.
If the outer repository already tracks anything under that directory, report the
overlap and resolve ownership before altering tracked content.

For a selected submodule connection:

- Preserve every child repository, commit, branch, remote, and uncommitted change.
  Do not reset, clean, switch branches, or advance the child as a side effect.
- If a remote is missing, offer a private repository with concrete names and obtain
  publication approval once, unless already authorized. Never use a machine-local
  path as the registered URL, and never embed credentials in `.gitmodules`.
- Register the child's real remote URL and reviewed commit. Confirm that the
  recorded commit is available on that remote. Report missing access or an
  unpublished commit as pending.
- Preserve existing `.gitmodules` entries. For an authorized conversion from
  ignored to submodule, adjust only the relevant ignore rule.
- The parent tracks `.gitmodules` and a Git link (index mode `160000`) for the
  child, never the child's source files. Verify this before committing outer
  changes.

If the outer workspace already uses Git, preserve its repository, remote, and
ignore rules. If initialization is needed, show the intended tracked paths and
ignore entries and obtain authorization before `git init`. A connection request
alone does not authorize creating a remote repository, committing, or pushing.

## Add the Memory Connection

`AGENTS.md` is the only canonical instruction file. Do not create a `CLAUDE.md`.

If the project has no `AGENTS.md`, propose a minimal file that contains only the
bridge below. If it already has one, preserve every existing instruction and add
the bridge only when an equivalent block is absent.

Compute the path from the instruction file's directory to the outer `wiki/index.md`.
For an immediate child whose instructions live at its root, the bridge is one line:

```markdown
Use `../wiki/index.md` as shared long-term memory when relevant; follow only relevant links and its write workflow for durable facts, decisions, and relationships. This project's files remain authoritative for current project state.
```

Adapt that path to the actual layout. Use a relative path when the project lives
inside the outer workspace. For an external project, do not invent `../wiki`. Point
at the confirmed outer wiki only in a way that resolves from that project, and
record the machine-specific location in `projects/local-paths.md`. Do not commit a
machine-local absolute path in a tracked file.

For a new repository created under an approved request, include the bridge in its
initial `AGENTS.md`. For an existing file, show the exact proposed diff and wait
for approval before editing. Do not copy wiki content into the project.

If the project already has a `CLAUDE.md`, leave its existing content in place. Do
not add a prose line that only says to read `AGENTS.md`. A user who needs
Claude-only notes can put this exact first line in that file:

```text
@AGENTS.md
```

That import is the escape hatch. With no `CLAUDE.md`, Claude Code loads `AGENTS.md`
natively. Show the proposed line and wait for approval before adding or editing
`CLAUDE.md`.

## Register and Verify

- Create or update `projects/<project-id>.md` from `projects/project-template.md`.
  Record the confirmed purpose, root-relative path (or external path-map
  reference), connection mode, sanitized remote URL or `NONE`, and verified remote
  default branch. Record an unresolved field as `UNKNOWN` with the reason. Do not
  leave a template placeholder.
- Add a compact Memory Connection section when the profile lacks one: status
  `CONNECTED`, `PENDING`, or `DECLINED`; canonical instruction path; relative wiki
  path; and the environment in which access was checked.
- Link the profile from `projects/index.md`. Preserve unrelated entries. Put a
  finished connection under Connected Projects and an unfinished one under Pending
  Intake.
- Cite project files or user confirmation for a durable fact. Ingest wiki knowledge
  only within the authorized scope and according to `wiki/SCHEMA.md`.
- Verify the instruction link from the target checkout. Confirm the outer
  repository ignores an independent child or records a submodule Git link.
- Reconcile the root `AGENTS.md` and the project profile with the final connection
  mode, path, remote, and remote default branch. Show a targeted correction to a
  stale claim. Do not record `UNKNOWN` when a read-only Git check can resolve the
  field.
- Report the current branch, cleanliness, ahead/behind state, divergence, and
  `git submodule status --recursive` in the verification report. Do not store those
  changing values as timeless profile facts. Do not silently change a checkout.
- Show the changed paths and the intended staging list. Stage only scoped,
  authorized changes. Confirm child source was not staged in the parent. Commit or
  push only after approval of the concrete reviewed diff.

When a submodule is selected, include these consequences in the handoff. A fresh
clone can use `git clone --recurse-submodules`. An existing clone can use
`git submodule update --init --recursive` when the user asks to synchronize.
Connecting an existing child does not reset that checkout. Commit and push in the
child first. The parent records the new child commit in a separate commit, when
authorized. A child push does not move the parent's pointer. Submodule checkout
often leaves a detached HEAD, so select or create the intended branch before new
work. Cloning only the child does not fetch the outer workspace or its shared
memory.

A separate clone or machine may not have the outer workspace beside the project.
Report the repository identity and the shared entry paths. Do not assume a relative
path is available there.

Report the profile path, connection mode, instruction change, and what was
verified.
