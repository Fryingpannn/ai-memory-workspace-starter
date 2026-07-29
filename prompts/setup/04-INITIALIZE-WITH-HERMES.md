# Stage 4: Initialize the Harness with Hermes

Use Hermes's native project initialization so the root `AGENTS.md` comes from the
workspace Hermes actually inspects. The current Codex or Claude task supervises this
one-time Hermes session and resumes setup afterward.

Hermes `/init` is the native file-initialization step. It scans the project with
read-only tools, creates a concise root `AGENTS.md`, or merge-updates an existing one.
It does not create `CLAUDE.md`, the portable root `USER.md`, or the wiki.

Upstream reference:
`https://github.com/NousResearch/hermes-agent/blob/main/hermes_cli/init_command.py`

## Preflight

1. Work from the confirmed outer workspace root.
2. Confirm Hermes is configured and that this folder is its active project and
   `terminal.cwd`.
3. Record whether a root `AGENTS.md` already exists.
4. Confirm the scaffold stage reserved a missing `AGENTS.md` for Hermes instead of
   copying the fallback template.

If `AGENTS.md` already existed before setup, explain that `/init` will merge-update it,
show the current path, and ask approval before running the command. If declined, keep it
unchanged and continue to Stage 5.

## Run One Supervised Hermes Session

Start an interactive Hermes session in the outer root. Do not transfer ownership of the
remaining setup to Hermes.

```text
hermes --cli
```

### User-profile onboarding

Ask Hermes to run the same short, consent-gated flow as its native first-contact
profile onboarding:

```text
Run the same short profile-build flow as your native first-contact onboarding before
project initialization. Offer it first and let me decline. If I accept, ask only for
what I am comfortable sharing: my name, what I do, and how I like you to work. Save
each confirmed durable fact to your user-profile memory. Do not perform external
lookups or read connected accounts unless I separately approve.
```

- Relay the questions and answers without exposing credentials.
- Let the user decline or skip any question.
- Keep the confirmed answers in the setup handoff for Stage 5.
- Hermes may store confirmed facts in its user-level profile memory.
- Do not copy or inspect that user-level memory file directly.
- Do not perform an external lookup during this tutorial.

If onboarding was already completed or the user declines, continue without repeating it.

### Initialize `AGENTS.md`

Run:

```text
/init This is a multi-project outer workspace for shared instructions and long-term memory. Treat immediate child repositories as separate projects. During this root initialization, use only their immediate names; do not inspect or edit their contents. Create or update only the root AGENTS.md. Keep it concise and focus on root routing, verified root commands, source-of-truth boundaries, and real pitfalls. Avoid recording transient setup state such as whether root Git, remotes, or profiles exist yet because later setup stages may change them.
```

Let Hermes inspect the workspace and finish the native `/init` turn. End the Hermes
session normally, then return control to the original Codex or Claude setup manager.

## Verify

Confirm:

- root `AGENTS.md` now exists, or the pre-existing file was explicitly preserved;
- the generated file is concise and based on observed workspace files;
- no child project file changed;
- no other workspace file changed during `/init`;
- confirmed onboarding answers are available for Stage 5 without asking twice.

If native `/init` is unavailable or fails after a bounded retry, copy
`templates/workspace/AGENTS.md` as a missing-only fallback, state that Hermes
initialization did not complete, and continue. Never replace an existing file with the
fallback.

Return `HERMES_INIT_COMPLETE`, the `AGENTS.md` outcome, and the confirmed onboarding
answers to the setup manager.
