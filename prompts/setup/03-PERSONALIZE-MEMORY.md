# Stage 3: Personalize the Memory Workspace

Run this after discovery and any existing-project intake.

## Ask Only for Missing Context

Gather only information not already confirmed from project sources:

- owner or team;
- major areas of work;
- important outputs;
- important person or role;
- the current priority project;
- one safe durable fact;
- one confirmed project decision;
- why the decision was made;
- the source or provenance for each durable claim.

Never ask the user to repeat information already confirmed.

## Personalize the Operating Files

1. Replace bracketed placeholders in `AGENTS.md`.
2. Update `README.md` with the workspace purpose and current priority.
3. Keep `CLAUDE.md` as a short bridge to `AGENTS.md`.
4. Make `projects/index.md` the project discovery route.
5. Make `projects/local-paths.md` the machine-local location route.

Keep project-specific details in project profiles, not in `AGENTS.md`.

## Seed Recent Memory

Create `memory/YYYY-MM-DD.md` for the setup date.

Include:

- setup mode;
- projects connected today;
- current priority;
- unresolved questions;
- next recommended action.

Do not duplicate stable facts that belong in the wiki.

## Seed Durable Memory

Update `wiki/pages/workspace-profile.md` with:

- owner or team;
- important person or role;
- current priority project;
- safe durable facts;
- provenance.

Update `wiki/pages/decisions.md` with each confirmed decision:

- decision;
- rationale;
- date;
- project ID;
- source or user confirmation.

Link new durable pages from `wiki/index.md`.
Add a dated entry to `wiki/log.md`.

Put uncertain or unprocessed information in `wiki/inbox.md`.

## Adapt Read and Write Routes

Ensure `AGENTS.md` tells agents:

- read `projects/index.md` to discover projects;
- read `projects/local-paths.md` to locate them on this machine;
- read the project profile before inspecting a connected project;
- treat connected project files as canonical for current project state;
- write recent cross-project context to `memory/`;
- write durable cross-project facts and decisions to `wiki/pages/`;
- never modify a connected project during setup.

## Final Review

1. Show all files changed.
2. Explain project discovery, local path lookup, memory read, and memory write-back in
   five lines or fewer.
3. Show `git diff --stat`.
4. Show `git status`.
5. Do not commit or push.
6. Stop for user review.
