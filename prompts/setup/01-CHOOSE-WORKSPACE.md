# Stage 1: Choose the Outer Workspace

This stage is read-only until the user confirms the target.

## Determine the Starting Case

Inspect only the current directory and its immediate children. Ask:

1. Do you already have one outer folder that contains the projects this workspace
   should remember?
2. If yes, what is its path?
3. If no, where should a new outer folder be created?

Infer answers from the current directory when safe, then ask for confirmation instead
of repeating known questions.

Supported cases:

- `EXISTING_OUTER`: use the confirmed existing folder.
- `NEW_OUTER`: create one new folder after approval.

Projects outside the chosen outer folder are out of scope for guided setup.

## Inspect the Candidate Root

Show:

- resolved path;
- whether it exists;
- whether it is already a Git repository;
- immediate files and folders only;
- whether `AGENTS.md`, `CLAUDE.md`, or `wiki/` already exist;
- any obvious file collisions with the starter.

Do not recursively scan project folders.

## Confirmation Gate

Use one concise intake question. Ask the user to confirm:

- the exact outer workspace root;
- permission to create it when missing;
- permission to add missing skeleton files later;
- permission to inspect selected project documentation read-only later.

When immediate child project folders are obvious, list them and ask whether all should
be analyzed later. Save that answer so Stage 5 does not ask again.

Return the confirmed root path to the setup manager.
