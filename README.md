# AI Memory Workspace Starter

A Hermes-friendly, files-first workspace that keeps useful context across fresh chats.

The workspace belongs to you, not to one model or app. Hermes, Codex, Claude Code, and
other file-aware agents can all use the same durable Markdown files.

## One-Prompt Setup

Install Hermes, open an empty working directory, run `hermes`, and paste:

```text
Set up my AI memory workspace from this repository:
https://github.com/Fryingpannn/ai-memory-workspace-starter

Start with prompts/START-HERE.md and follow the complete setup workflow.
Ask only the questions you cannot answer safely. Do not move or modify my existing
projects without approval.
```

The agent will:

1. Inspect the repository link.
2. Ask where the workspace should live.
3. Create a private GitHub copy or offer local-only setup.
4. Clone and validate the workspace.
5. Detect the user's project layout.
6. Connect approved projects read-only.
7. Personalize the workspace and memory.
8. Stop for review before commit or push.
9. Prepare the fresh-session verification.

GitHub CLI must be authenticated for automatic private-repository creation. Otherwise
the agent will pause for login, ask the user to use the template button, or continue
locally with pushes to the public starter disabled.

## Manual Setup Alternative

1. Complete the [official Hermes quickstart](https://hermes-agent.nousresearch.com/docs/getting-started/quickstart/) and run `hermes setup`.
2. Use this repository as a GitHub template to create your own private repository.
3. Clone your new repository and open its folder in a terminal.
4. Run `hermes`.
5. Tell Hermes:

   `Read prompts/START-HERE.md and set up this workspace.`

6. Inspect every changed file.
7. Create the first local Git checkpoint, then push to your private GitHub repository.
8. Open a fresh session and run `prompts/VERIFY-WORKSPACE.md`.

Hermes does not own the resulting memory. It helps create and maintain ordinary files
inside your Git repository.

## Existing Projects

You do not need to move existing repositories into this starter.

The setup flow detects whether you have:

- one existing project;
- an outer folder containing several projects;
- an outer folder that is itself a Git repository;
- projects scattered across different locations;
- a mix of new and existing work.

By default, existing projects stay where they are. Hermes creates:

- a tracked project registry;
- one tracked profile per connected project;
- a gitignored local path map for this machine;
- sourced memory from selected high-signal documentation.

Initial setup connects at most three projects and reads only approved documentation.
It does not broadly ingest source code or edit connected repositories.

### Recommended Universal Layout

If the existing outer folder is not a Git repository, place the memory workspace beside
the project repositories inside it:

```text
My-Work/
├── memory-workspace/
├── client-portal/
└── automations/
```

If the existing outer folder is already a Git repository, place the memory workspace
beside that outer repository instead of nesting another tracked repository inside it.

This sidecar layout works without moving existing projects.

## Workspace Map

```text
.
├── AGENTS.md                  canonical operating instructions
├── CLAUDE.md                  Claude Code compatibility bridge
├── memory/                    recent dated working context
├── wiki/
│   ├── index.md               durable knowledge map
│   ├── inbox.md               unsynthesized material
│   ├── log.md                 durable change history
│   ├── pages/                 durable facts and decisions
│   └── raw/                   auditable source records
├── projects/
│   ├── index.md               tracked project registry
│   ├── <project-id>.md        tracked project profile
│   └── local-paths.md         gitignored machine-local paths
├── docs/                      operating references
├── skills/                    reusable procedures
├── outputs/                   reviewable deliverables
└── prompts/
    ├── START-HERE.md          one-prompt bootstrap
    ├── HERMES-SETUP.md        staged setup router
    └── setup/                 short setup stages
```

## Memory Model

- Current chat is temporary.
- `memory/YYYY-MM-DD.md` holds recent working context.
- `wiki/pages/` holds durable facts and decisions.
- `wiki/raw/` preserves source records and provenance.
- Connected project files hold current project state.
- `projects/` holds project discovery profiles and local path routing.
- `outputs/` holds deliverables, not memory.

Vector search, RAG, databases, knowledge graphs, and automations are intentionally
excluded from this beginner starter.

## Definition of Done

The workspace is ready when a fresh session can:

1. Explain what the workspace is for.
2. Identify important projects and people or roles.
3. Follow the operating rules in `AGENTS.md`.
4. Retrieve one durable decision and name its source file.
5. Write one new dated memory to the correct file.

## Safety

Keep passwords, API keys, tokens, credentials, and secret environment files out of Git.
Use safe or fictional data while learning.
