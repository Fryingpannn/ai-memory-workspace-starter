# Fresh-Session Verification Prompt

Close the setup session and start a visibly fresh session at the repository root. Replace
`[DATE]` before pasting.

```text
Treat this as a fresh session. Do not rely on earlier chat history.

Read the workspace and tell me:
1. What this workspace is for
2. Which projects are connected according to projects/index.md
3. Which profile describes each connected project
4. Where this machine stores the local project paths
5. Which people or roles are important
6. Which operating rules you must follow
7. One durable decision and the file where you found it

Then record this test memory in the correct place:
"The workspace verification test was completed on [DATE]."

Show exactly which file you changed and why. If the workspace does not contain enough
information, stop and list what is missing.
```

The test passes when:

- the answer cites local files;
- connected projects are found through the registry and profiles;
- machine-specific paths come only from the gitignored local path map;
- the only new change is the expected dated memory note.
