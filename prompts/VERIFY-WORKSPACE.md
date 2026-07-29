# Fresh-Session Verification

Start a fresh file-aware agent session at the outer workspace root. Replace `[DATE]`,
then paste:

```text
Treat this as a fresh session. Do not rely on earlier chat history.

Read the workspace and tell me:
1. What you know about the user and how they prefer agents to work
2. What this outer workspace is for
3. Which projects are registered
4. How wiki/index.md and wiki/SCHEMA.md route long-term memory
5. One important relationship between two projects, entities, or decisions
6. The local source files supporting that relationship
7. Which operating rules you must follow

Then append this maintenance entry to `wiki/log.md` and show exactly what changed:
"The workspace verification test was completed on [DATE]."

If the workspace does not contain enough information, stop and list what is missing.
```

The test passes when:

- a root `AGENTS.md` created during setup contains one short summary plus `Memory
  Reads`, `Memory Writes`, `Repository Map`, and `Working Style`, without redundant
  routing, Commands, Source-of-Truth, Privacy, or Pitfalls sections;
- when `AGENTS.md` existed before setup, the final file contains every original
  instruction plus the user-approved fused additions, and `AGENTS.proposed.md` is gone;
- `CLAUDE.md` delegates to `AGENTS.md` instead of maintaining competing rules;
- user context comes from the root `USER.md`;
- `USER.md` is under 100 lines and contains only compact, durable, user-confirmed
  information;
- durable knowledge lookup starts from `wiki/index.md`;
- durable claims cite wiki pages and their source paths;
- project discovery uses `projects/index.md` when projects exist;
- each in-workspace project profile uses its real root-relative path;
- project remote, remote default branch, and connection mode match live read-only Git
  checks;
- no profile points to a missing file;
- no unresolved bracketed placeholder remains in `USER.md`,
  `wiki/pages/workspace-profile.md`, or registered project profiles; exclude the
  reusable `projects/project-template.md`;
- `UNKNOWN` is used only when the relevant source or live read-only check truly cannot
  answer the field;
- the parent and recursive submodule status are reported when submodules exist;
- only the expected `wiki/log.md` verification entry is added.

If any check fails, do not record the completion sentence. Report the mismatch, repair
it through the relevant setup stage, and rerun this test from another fresh session.

When repaired verification changes will be committed, show every exact path and a
one-line factual summary before requesting approval. Do not ask approval using only a
file count.

After the test passes, return `WORKSPACE_VERIFIED`. Do not remove the temporary setup
clone yet; the final inner-project handoff prompt owns cleanup.
