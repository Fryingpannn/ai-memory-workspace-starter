# AI Memory Workspace Starter

A files-first outer workspace that gives Codex, Claude, Hermes, and other file-aware
agents the same long-term Markdown memory.

## One Setup Prompt

Paste this into the agent you already use:

```text
Set up my AI memory workspace from this repository:
https://github.com/Fryingpannn/ai-memory-workspace-starter

Read SETUP.md from GitHub before cloning. If a clone is needed, use a temporary staging
directory, not my current folder. Then follow the setup index.
```

The agent asks whether you already have one outer workspace folder.

- If yes, it adds only missing skeleton files to that folder.
- If no, it helps create one.
- Existing project folders stay in place.
- Projects scattered outside that outer folder are not part of the guided setup.

The public starter is cloned only as an instruction and template source. It is not
personalized or used as the user's long-term workspace.

## Setup Flow

1. Choose or create one outer workspace.
2. Install and configure Hermes on the system, then register the outer folder as its
   active project.
3. Add supporting skeleton files while reserving a missing root `AGENTS.md` for Hermes.
4. Run one supervised Hermes session in the outer folder:
   - complete or decline Hermes's profile onboarding;
   - run native `/init` so Hermes creates or merge-updates root `AGENTS.md`, unless the
     user explicitly preserves a pre-existing file.
5. Return to the original Codex or Claude manager; Hermes does not take over.
6. Build a short, user-approved root `USER.md` from the confirmed onboarding answers.
7. Build the root `wiki/` using the
   [LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).
8. Analyze up to three approved project folders with read-only subagents.
9. Integrate sourced project knowledge into the wiki.
10. Add the shared memory block to the Hermes-generated `AGENTS.md`.
11. Keep `CLAUDE.md` as a compatibility bridge to canonical `AGENTS.md`.
12. Choose whether child Git repositories stay independent or become submodules.
13. Initialize or review the outer workspace Git repository.
14. Verify retrieval from a fresh session.

## Outer Workspace

The intended layout is:

```text
My-Workspace/
├── AGENTS.md
├── CLAUDE.md
├── USER.md
├── wiki/
├── memory/
├── projects/                  metadata registry, not project source
├── prompts/
├── client-portal/
└── automations/
```

`client-portal/` and `automations/` may keep their own Git histories. Setup explicitly
offers two modes: keep child repositories independent and ignored, or register them as
Git submodules when portability is worth the additional Git complexity.

If the outer folder already uses Git, setup preserves its repository and remote. If it
does not, setup applies the reviewed child-repository mode before asking to run
`git init`.

## Wiki Model

The root wiki follows three layers:

- `wiki/raw/`: preserved source records;
- `wiki/pages/`: maintained synthesis and relationships;
- `wiki/SCHEMA.md`: instructions for ingesting, querying, linking, and linting.

`wiki/index.md` is the long-term-memory entrypoint. `wiki/log.md` records dated wiki
changes. The interlinked Markdown pages act as the knowledge graph; vector search and a
graph database are not required.

The root `USER.md` is the portable user profile shared by file-aware harnesses.
`wiki/index.md` links to it instead of duplicating those facts in a wiki page.

## Existing AGENTS.md and CLAUDE.md

A missing `AGENTS.md` is created by Hermes `/init`; the starter version is fallback-only.
When `AGENTS.md` already exists, Hermes `/init` can merge-update it only after the user
approves. Existing content is not replaced.

After the wiki exists, setup shows the concise shared-routing block before merging it
into canonical `AGENTS.md`. `CLAUDE.md` points to `AGENTS.md` instead of duplicating
those rules.

```text
Read AGENTS.md. It is the canonical entry document for this workspace. Everything there applies here.
```

## Safety

- Existing projects remain unchanged during setup.
- Project workers read only approved, high-signal files.
- Secrets, credentials, dependency trees, build outputs, and large data are excluded.
- The user reviews changes before Git initialization, commit, remote creation, or push.
