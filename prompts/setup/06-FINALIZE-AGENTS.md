# Stage 6: Finalize Workspace Instructions

Create one canonical root `AGENTS.md` that combines any existing instructions with the
workspace template. Do not maintain competing instruction files.

The final file should include:

- a short workspace summary;
- `Memory Reads`;
- `Memory Writes`;
- `Repository Map`;
- `Working Style`;
- every instruction that existed in the user's original `AGENTS.md`.

Use confirmed preferences from `USER.md`, the final wiki paths, and observed immediate
child-repository names. Keep the additions concise.

## If AGENTS.md Was Created From the Template

Personalize it in place. Replace generic repository-map entries with the observed
workspace folders and child repositories where helpful. Show the exact diff.

## If AGENTS.md Existed Before Setup

1. Leave the original `AGENTS.md` unchanged.
2. Create `AGENTS.proposed.md` beside it.
3. Copy every original instruction into the proposal without silently deleting or
   weakening anything.
4. Add only missing memory-read, memory-write, repository-map, and working-style
   guidance from `templates/workspace/AGENTS.md`.
5. Remove duplication inside the proposal only when the meaning is fully preserved.
6. Show the complete proposal and an exact diff against the original.
7. Ask the user to review and confirm the replacement.
8. Only after confirmation, verify the proposal still contains every original
   instruction, delete the old `AGENTS.md`, and rename `AGENTS.proposed.md` to
   `AGENTS.md`.
9. Verify the final file exists at the canonical path and the proposal file is gone.

If the user declines or requests changes, keep the original file and revise or remove
only the proposal. Never delete the original before confirmation.

## CLAUDE.md Compatibility Bridge

`AGENTS.md` remains canonical. A missing `CLAUDE.md` receives:

```text
Read AGENTS.md. It is the canonical entry document for this workspace. Everything there applies here.
```

If `CLAUDE.md` existed before setup and lacks an equivalent reference, show that line
and its insertion location, then ask before adding it. Do not copy the full routing
content into `CLAUDE.md`.

Return the exact final paths and diff before continuing.
