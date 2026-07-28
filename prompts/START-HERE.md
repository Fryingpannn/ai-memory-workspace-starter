# One-Prompt Workspace Bootstrap

This is the entry point when the user provides a repository URL or says
"set up this repository."

This file may be read from GitHub before the repository exists locally.

## Precondition

If this file is being read by another agent and the `hermes` command is unavailable,
follow `prompts/INSTALL-HERMES.md` first and stop at its handoff. Resume this file from
a real Hermes session.

## Goal

Create or open the user's private memory-workspace repository, then run the staged
Hermes setup without requiring the user to understand the internal files.

## Required User Input

The initial message should contain a repository URL.

Recommended message:

```text
Set up my AI memory workspace from this repository:
[REPOSITORY URL]

Start with prompts/START-HERE.md and follow the complete setup workflow.
Ask only the questions you cannot answer safely. Do not move or modify my existing
projects without approval.
```

## Safety Rules

- Inspect repository metadata before cloning or editing.
- Never personalize memory directly in a public starter repository.
- Never overwrite a non-empty destination folder.
- Never delete or replace an existing Git remote without approval.
- Never move, copy, or edit existing projects during bootstrap.
- Never read secrets or broad source trees during project intake.
- Ask before creating a GitHub repository, commit, push, or other external change.

## Step 1: Inspect the Repository URL

Determine:

- repository owner and name;
- visibility;
- whether it is a template;
- whether it appears to be the public starter or the user's private copy;
- default branch.

Classify it:

- `PUBLIC_STARTER`: public template or public starter source.
- `PRIVATE_COPY`: private repository that will own the user's memory.
- `LOCAL_ROOT`: the current directory is already a valid workspace clone.
- `UNKNOWN`: ownership or destination is ambiguous.

Do not clone until the classification and destination are clear.

## Step 2: Ask the Bootstrap Questions

Ask only what cannot be determined:

1. Where should the workspace be cloned locally?
2. May setup create a private GitHub repository named `ai-memory-workspace`, or should
   this remain local-only?

Do not ask for a repository name during local-only setup. Ask for a different private
repository name only when the recommended name conflicts or the user rejects it.

Recommend:

- repository name: `ai-memory-workspace`;
- visibility: private;
- destination: a new empty folder;
- no public push of personalized memory.

Do not ask project-intake questions yet. The discovery stage handles them after clone.

## Step 3: Create or Open the Workspace

### LOCAL_ROOT

Confirm the root contains:

- `README.md`;
- `AGENTS.md`;
- `prompts/HERMES-SETUP.md`.

Do not clone again.

### PRIVATE_COPY

Confirm the destination does not already contain unrelated files.
Clone the private repository into the approved destination.

### PUBLIC_STARTER

Check whether GitHub CLI is installed and authenticated.

If authenticated and the user approves creating a private repository, use the starter
as a GitHub template and clone the new private repository.

Example shape:

```text
gh repo create OWNER/REPO --private --template STARTER_OWNER/STARTER_REPO --clone
```

Resolve the exact owner, names, and working directory before running it.

If GitHub CLI is unavailable, offer:

- pause for GitHub login;
- ask the user to create a private copy with "Use this template";
- local-only setup.

For local-only setup:

1. Clone the public starter to the approved empty destination.
2. Rename remote `origin` to `starter`.
3. Disable pushes to the public starter:

   ```text
   git remote set-url --push starter disabled://public-starter
   ```

4. Confirm the `starter` fetch URL is public and its push URL is disabled.
5. Do not create another remote or push.
6. Explain that the workspace is not backed up until a private remote is added.

### UNKNOWN

Stop and explain exactly what could not be determined.

## Step 4: Validate the Local Clone

Inside the workspace root:

1. Print the working directory.
2. Show the repository fetch and push URLs and visibility destination.
3. Confirm the root contains the required starter files.
4. Confirm personalized memory will not be pushed to the public starter.
5. Read `AGENTS.md`.
6. Read `prompts/HERMES-SETUP.md`.

## Step 5: Run the Staged Setup

Follow `prompts/HERMES-SETUP.md` from the beginning.

Let its discovery stage:

- detect new or existing projects;
- classify outer-folder and scattered-project scenarios;
- ask the project-specific questions;
- connect approved projects read-only;
- personalize memory;
- prepare fresh-session verification.

Do not duplicate those questions during bootstrap.

## Step 6: Review and Save

After the staged setup stops for review:

1. Show every changed file.
2. Show `git diff --stat` and `git status`.
3. Confirm `projects/local-paths.md` is ignored.
4. Ask whether the user approves the first commit.
5. If approved, commit only the reviewed workspace files.
6. Ask separately before pushing to the private remote.
7. Never push personalized memory to the public starter.

## Step 7: Fresh-Session Proof

Tell the user to open a visibly fresh agent session in the workspace root and say:

```text
Read prompts/VERIFY-WORKSPACE.md and run the fresh-session verification.
```

Do not claim long-term memory is working until that fresh-session test passes.
