# Connect Projects

The outer workspace receives `skills/connect-project/SKILL.md` during scaffolding.
That skill is the procedure for connecting a child or existing project. Do not
deliver a copy-paste prompt, and do not ask the user to open another session to
paste one.

After fresh-session verification:

- Confirm `skills/connect-project/SKILL.md` exists in the outer workspace and the
  root `AGENTS.md` says when to use it.
- If the user has already asked to connect specific projects, follow that skill for
  each one. Wait for approval before editing a project.
- If the user has not asked, leave the skill in place for a later session.

After this handoff, remove the temporary setup clone only when the agent created it
for this workflow. Report the removed path. Never remove a clone supplied by the
user.
