# Stage 6: Finalize Workspace Instructions

Create one canonical root `AGENTS.md` that combines any existing instructions with the
workspace template. Do not maintain competing instruction files.

The final file should include:

- a short workspace summary;
- `Memory Reads`;
- `Memory Writes`;
- `Repository Map`;
- `Skills`, including when to use `skills/connect-project/SKILL.md`;
- `Working Style`;
- every instruction that existed in the user's original `AGENTS.md`.

Use confirmed preferences from `USER.md`, the final wiki paths, and observed immediate
child-repository names. Keep the additions concise.

## If AGENTS.md Was Created From the Template

Personalize it in place. Replace generic repository-map entries with the observed
workspace folders and child repositories where helpful. Keep the Skills section.
Show the exact diff.

## If AGENTS.md Existed Before Setup

1. Leave the original `AGENTS.md` unchanged.
2. Create `AGENTS.proposed.md` beside it.
3. Copy every original instruction into the proposal without silently deleting or
   weakening anything.
4. Add only missing memory-read, memory-write, repository-map, skills, and
   working-style guidance from `templates/workspace/AGENTS.md`. Keep the
   connect-project skill reference.
5. Remove duplication inside the proposal only when the meaning is fully preserved.
6. Show the complete proposal and an exact diff against the original.
7. Ask the user to review and confirm the replacement.
8. Only after confirmation, verify the proposal still contains every original
   instruction, delete the old `AGENTS.md`, and rename `AGENTS.proposed.md` to
   `AGENTS.md`.
9. Verify the final file exists at the canonical path and the proposal file is gone.

If the user declines or requests changes, keep the original file and revise or remove
only the proposal. Never delete the original before confirmation.

## No CLAUDE.md

Do not create a `CLAUDE.md`. `AGENTS.md` is the only canonical instruction file.
Claude Code loads it natively when no `CLAUDE.md` or `CLAUDE.local.md` is present in
the working directory or above it. A prose line that says to read `AGENTS.md` does
not load that file, and a `CLAUDE.md` blocks native loading in this directory and in
nested child projects.

Preserve a `CLAUDE.md` that already exists. A user who needs Claude-only notes can
add one whose first line is `@AGENTS.md` (those characters, not wrapped in
backticks). That import is how Claude Code reads the canonical file when a
`CLAUDE.md` is present. Show that change and wait for approval. Do not copy
workspace routing into `CLAUDE.md`.

Return the exact final paths and diff before continuing.
