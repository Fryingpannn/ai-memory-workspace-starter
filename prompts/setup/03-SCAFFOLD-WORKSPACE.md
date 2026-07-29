# Stage 3: Add the Workspace Skeleton

Use the temporary starter clone as the source and the confirmed outer folder as the
target.

Spawn one clean-context scaffold subagent when supported. Give it only:

- the starter staging path;
- the confirmed outer workspace path;
- this prompt;
- the user's approved collision policy.

## Merge Rules

- Copy missing skeleton files only.
- Never replace, truncate, or silently merge an existing file.
- Never copy the starter's `.git/` directory or remote.
- Never edit an existing project folder.
- Preserve existing `AGENTS.md`, `CLAUDE.md`, `README.md`, `.gitignore`, and `wiki/`.
- Record every collision for review.

The desired root skeleton is:

```text
AGENTS.md
CLAUDE.md
SETUP.md
docs/
memory/
outputs/
projects/
prompts/
skills/
wiki/
```

If `AGENTS.md` or `CLAUDE.md` is absent, add the starter default. If either exists,
leave it byte-for-byte unchanged; Stage 6 handles the optional one-line memory route.

When an existing directory such as `wiki/` is present, add only missing files after
showing the exact proposed paths. Do not replace existing pages.

After copying, verify that the target contains `SETUP.md` and every routed prompt.
Continue from the target copy. Remove only the agent-created temporary clone after it
is no longer needed; never remove a clone supplied by the user.

## Review

Return:

- files created;
- files skipped because they already existed;
- unresolved collisions;
- confirmation that no existing project file changed.

The manager resolves any collision with the user before continuing.
