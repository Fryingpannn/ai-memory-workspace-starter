# Stage 2: Add the Workspace Skeleton

Use `templates/workspace/` inside the temporary setup clone as the scaffold source. The
confirmed outer folder is the target.

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
  `wiki/` byte-for-byte during this stage.
- Record every collision for review.

The desired root skeleton is:

```text
.gitignore
AGENTS.md
CLAUDE.md
USER.md
README.md
outputs/
projects/
skills/
wiki/
```

Copy each missing file or folder from the workspace template. If root `AGENTS.md` is
missing, copy `templates/workspace/AGENTS.md`; Stage 6 personalizes it after user and
project context are known. If `AGENTS.md` already exists, preserve it for the reviewed
fusion in Stage 6.

When an existing directory such as `wiki/` is present, add only missing files after
showing the exact proposed paths. Do not replace existing pages.

After copying, verify that the target contains the expected supporting scaffold without
any installer-only files. Continue working in the target, but keep reading later prompts
from the temporary setup clone through final verification.

## Review

Return:

- files created;
- files skipped because they already existed;
- whether `AGENTS.md` was created from the template or preserved for later fusion;
- unresolved collisions;
- confirmation that no installer prompt, repository metadata, or remote was copied;
- confirmation that no existing project file changed.

The manager resolves any collision with the user before continuing.
