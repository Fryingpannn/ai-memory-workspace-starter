# Hermes Workspace Setup Prompt

Use this after cloning your copy of the starter repository and starting Hermes from its
root folder.

```text
Personalize this files-first AI memory workspace for me.

Before editing:
1. Print the current working directory.
2. Confirm it is the Git repository root containing README.md and AGENTS.md.
3. List the files you plan to change.
4. Stop if the directory is wrong, a target file is missing, or an edit would destroy
   existing work.

Ask me only for information that is still missing:
- Owner or team
- Areas of work
- Important outputs
- Important person or role
- Active project
- One safe durable fact
- One real project decision
- Why that decision was made
- A source or provenance note

Then:
1. Replace the bracketed placeholders in AGENTS.md.
2. Update README.md with my workspace purpose and active project.
3. Record the safe durable fact in wiki/pages/workspace-profile.md.
4. Record the real decision, rationale, date, and provenance in
   wiki/pages/decisions.md.
5. Link both pages from wiki/index.md.
6. Add a dated setup entry to wiki/log.md.
7. Leave CLAUDE.md as the short bridge to AGENTS.md.
8. Do not add databases, vector search, RAG, automations, nested repositories, or
   submodules.
9. Do not stage, commit, create a remote, push, publish, or expose secrets.

When finished:
1. Show the files changed.
2. Explain the read route and write-back route in five lines or fewer.
3. Show git status.
4. Stop for my review.
```

