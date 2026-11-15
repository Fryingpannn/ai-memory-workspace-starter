# Installer Repository Instructions

This repository is a setup package, not a personalized memory workspace.

## Start Here

1. Read `SETUP.md` for the routed installation workflow.
2. Read only the next prompt under `prompts/setup/`.
3. Use `templates/workspace/` only as the missing-file scaffold source.

## Boundaries

- Never personalize this repository for the user.
- Never copy its `.git/` directory or remote into the user's workspace.
- Never treat root files as the user's memory.
- Preserve existing target files; templates are missing-only defaults.
- Create a missing target `AGENTS.md` from the template.
- For an existing target `AGENTS.md`, create a complete fused proposal and replace the
  original only after explicit user review and confirmation.
- Do not create a target `CLAUDE.md`. `AGENTS.md` is the only canonical instruction
  file. A user who needs Claude-only notes can add a `CLAUDE.md` whose first line is
  `@AGENTS.md`.
- Connect a child or existing project with
  `templates/workspace/skills/connect-project/SKILL.md`. Do not deliver a paste
  prompt for that procedure.
- Keep setup prompts concise and update every route when stages move.
- Verify links, template paths, and a fresh remote clone before publishing changes.
