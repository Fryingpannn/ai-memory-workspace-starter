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
- Preserve existing `AGENTS.md`, `CLAUDE.md`, `USER.md`, `README.md`, `.gitignore`, and
  `wiki/`.
- When root `AGENTS.md` is missing, reserve that path for Hermes `/init` in Stage 4.
  Do not copy the starter fallback yet.
- Record every collision for review.

The desired root skeleton is:

```text
.gitignore
AGENTS.md
CLAUDE.md
USER.md
README.md
SETUP.md
docs/
memory/
outputs/
projects/
prompts/
skills/
wiki/
```

If `.gitignore`, `README.md`, `CLAUDE.md`, or `USER.md` is absent, add the starter
default. If any exists, leave it byte-for-byte unchanged. Stage 4 creates a missing
`AGENTS.md` through Hermes `/init`; the starter version is fallback-only. Stage 5
personalizes a new `USER.md`, and Stage 8 links the Hermes harness to shared memory.

When an existing directory such as `wiki/` is present, add only missing files after
showing the exact proposed paths. Do not replace existing pages.

After copying, verify that the target contains `SETUP.md` and every routed prompt.
Record whether `AGENTS.md` was preserved or reserved for Hermes. Continue from the
target copy. Keep the agent-created temporary clone until Stage 4 confirms native
`/init` or copies the fallback `AGENTS.md`. Remove it only after it is no longer needed;
never remove a clone supplied by the user.

## Review

Return:

- files created;
- files skipped because they already existed;
- whether `AGENTS.md` was preserved or reserved for Hermes `/init`;
- unresolved collisions;
- confirmation that no existing project file changed.

The manager resolves any collision with the user before continuing.
