# Hermes Workspace Setup Router

Use this after `prompts/START-HERE.md` has created or opened the user's private
workspace clone.

The user can say:

```text
Set up this workspace. I may already have projects. Detect my layout, ask only the
questions you need, and do not move or link anything without my approval.
```

## Setup Goal

Create a files-first memory workspace that can understand new or existing projects
without forcing the user to reorganize them.

## Non-Negotiable Defaults

- Do not move, copy, rename, symlink, delete, or rewrite an existing project.
- Do not add nested repositories, submodules, databases, vector search, or RAG.
- Do not scan the home directory or unrelated folders.
- Do not read `.env`, credentials, tokens, private keys, or secret folders.
- Do not edit files inside a connected project during setup.
- Do not stage, commit, push, publish, or create remotes.
- Prefer a project registry plus a local path map over symlinks.
- Ask before any action that changes existing work.

## Routed Workflow

Follow these files in order. Read only one stage at a time.

1. Read `prompts/setup/01-DISCOVER.md`.
2. Show the detected scenario and recommended setup mode.
3. Wait for the user to confirm the mode and project scope.
4. If existing projects will be connected, read
   `prompts/setup/02-CONNECT-PROJECTS.md`.
5. Read `prompts/setup/03-PERSONALIZE-MEMORY.md`.
6. Run `prompts/VERIFY-WORKSPACE.md`.
7. Show changed files and `git status`, then stop for review.

Read `prompts/setup/04-OPTIONAL-REORGANIZE.md` only when the user explicitly asks
to move, copy, symlink, nest, or consolidate repositories.

## Supported Scenarios

- New workspace with no existing projects.
- One existing project repository.
- Existing outer folder containing several project folders.
- Existing outer folder that is itself a Git repository.
- Projects scattered across different folders or drives.
- Mixed setup with both new and existing projects.

## Success Condition

The finished workspace must know:

- what projects exist;
- where each project is located on this machine;
- which files are authoritative for each project;
- what durable facts and decisions are confirmed;
- when to read recent memory versus the wiki;
- how to verify the setup from a fresh session.
