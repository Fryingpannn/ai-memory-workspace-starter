# Fresh-Session Verification Prompt

Close the setup session and start a visibly fresh session at the repository root. Replace
`[DATE]` before pasting.

```text
Treat this as a fresh session. Do not rely on earlier chat history.

Read the workspace and tell me:
1. What this workspace is for
2. Which projects and people or roles are important
3. Which operating rules you must follow
4. One durable decision and the file where you found it

Then record this test memory in the correct place:
"The workspace verification test was completed on [DATE]."

Show exactly which file you changed and why. If the workspace does not contain enough
information, stop and list what is missing.
```

The test passes when the answer cites local files and the only new change is the expected
dated memory note.

