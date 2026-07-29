# Optional Inner-Project Memory Bridge

Deliver this handoff only after the outer workspace passes fresh-session verification.
Do not edit any child project automatically.

List the registered child projects, then tell the user to open their agent inside each
project they want to connect and paste:

```text
Connect this project to the shared memory workspace in its parent folder.

Review this project's existing AGENTS.md and CLAUDE.md. Propose the smallest
non-duplicative addition to the canonical instruction file so future agents know:

- The outer workspace's long-term memory starts at `../wiki/index.md`.
- Read it only when relevant cross-project or durable context is needed, then follow
  only relevant links.
- For durable facts, decisions, or relationships learned while working here, follow
  the write workflow in `../wiki/index.md`.
- This project's own files remain authoritative for its current code and behavior.

Use relative paths, preserve every existing instruction, and do not copy wiki content
into this project. Show me the exact proposed diff and wait for my approval before
editing anything.

If neither AGENTS.md nor CLAUDE.md exists, propose a minimal AGENTS.md containing only
this bridge.
```

Explain that the resulting instruction will usually be one concise line:

```markdown
Use `../wiki/index.md` as shared long-term memory when relevant; follow only relevant links and its write workflow for durable facts, decisions, and relationships. This project's files remain authoritative for current project state.
```

If no child projects are registered, give the prompt once for later use.

After delivering the prompt, remove the temporary setup clone only when the agent
created it for this workflow. Report the removed path. Never remove a clone supplied by
the user.
