# Fresh-Session Verification

Start a fresh Codex, Claude, or other file-aware agent session at the outer workspace
root. Replace `[DATE]`, then paste:

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

Then record:
"The workspace verification test was completed on [DATE]."

Put it in the correct recent-memory file and show exactly what changed. If the workspace
does not contain enough information, stop and list what is missing.
```

The test passes when:

- user context comes from the root `USER.md`;
- durable knowledge lookup starts from `wiki/index.md`;
- durable claims cite wiki pages and their source paths;
- project discovery uses `projects/index.md` when projects exist;
- each in-workspace project profile uses its real root-relative path;
- project remote, remote default branch, and connection mode match live read-only Git
  checks;
- no profile points to a missing file;
- no unresolved bracketed starter placeholder remains in `USER.md` or project profiles;
- `UNKNOWN` is used only when the relevant source or live read-only check truly cannot
  answer the field;
- the parent and recursive submodule status are reported when submodules exist;
- only the expected dated recent-memory entry is added.

If any check fails, do not record the completion sentence. Report the mismatch, repair
it through the relevant setup stage, and rerun this test from another fresh session.
