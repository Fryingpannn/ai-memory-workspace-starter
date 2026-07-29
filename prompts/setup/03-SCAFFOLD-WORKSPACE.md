# Stage 3: Add the Workspace Skeleton

Use `templates/workspace/` inside the temporary setup clone as the only scaffold source.
The confirmed outer folder is the target.

Spawn one clean-context scaffold subagent when supported. Give it only:

- the setup staging path;
- the confirmed outer workspace path;
- this prompt;
- the user's approved collision policy.

## Merge Rules

- Copy missing skeleton files only.
- Never replace, truncate, or silently merge an existing file.
- Never copy repository-root installer files, prompts, docs, `.git/`, or its remote.
- Never edit an existing project folder.
- Preserve existing `AGENTS.md`, `CLAUDE.md`, `USER.md`, `README.md`, `.gitignore`, and
  `wiki/`.
- When root `AGENTS.md` is missing, reserve that path for Hermes `/init` in Stage 4.
  Do not copy the fallback template yet.
- Record every collision for review.

The desired root skeleton is:

```text
.gitignore
AGENTS.md
CLAUDE.md
USER.md
README.md
memory/
outputs/
projects/
skills/
wiki/
```

If `.gitignore`, `README.md`, `CLAUDE.md`, or `USER.md` is absent, add the workspace
template default. If any exists, leave it byte-for-byte unchanged. Stage 4 creates a
missing `AGENTS.md` through Hermes `/init`; its template is fallback-only. Stage 5
personalizes a new `USER.md`, and Stage 8 links the Hermes harness to shared memory.

When an existing directory such as `wiki/` is present, add only missing files after
showing the exact proposed paths. Do not replace existing pages.

After copying, verify that the target contains the expected supporting scaffold without
any installer-only files. Record whether `AGENTS.md` was preserved or reserved for
Hermes. Continue working in the target, but keep reading later prompts from the
temporary setup clone. Keep that clone through final verification.

## Review

Return:

- files created;
- files skipped because they already existed;
- whether `AGENTS.md` was preserved or reserved for Hermes `/init`;
- unresolved collisions;
- confirmation that no installer prompt, repository metadata, or remote was copied;
- confirmation that no existing project file changed.

The manager resolves any collision with the user before continuing.
