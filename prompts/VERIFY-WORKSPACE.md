# Fresh-Session Verification

Start a fresh Codex, Claude, or other file-aware agent session at the outer workspace
root. Replace `[DATE]`, then paste:

```text
Treat this as a fresh session. Do not rely on earlier chat history.

Read the workspace and tell me:
1. What this outer workspace is for
2. Which projects are registered
3. How wiki/index.md and wiki/SCHEMA.md route long-term memory
4. One important relationship between two projects, entities, or decisions
5. The local source files supporting that relationship
6. Which operating rules you must follow

Then record:
"The workspace verification test was completed on [DATE]."

Put it in the correct recent-memory file and show exactly what changed. If the workspace
does not contain enough information, stop and list what is missing.
```

The test passes when:

- the answer starts from `wiki/index.md`;
- durable claims cite wiki pages and their source paths;
- project discovery uses `projects/index.md` when projects exist;
- only the expected dated recent-memory entry is added.
