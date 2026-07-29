# Stage 2: Install and Configure Hermes

The current Codex, Claude, or other agent runs this stage. Do not transfer the setup to
a Hermes chat.

## Required Local Capabilities

- File Operations and Terminal
- browser automation through local Google Chrome
- built-in memory capture and session search
- skills
- cron

Standalone web-search providers, messaging gateways, external memory services, MCP,
voice, and other integrations are outside this tutorial.

## Install

1. Check `command -v hermes` and `hermes --version` first.
2. Open the current official installation page directly in the user's default browser,
   preferring Google Chrome when available:
   `https://hermes-agent.nousresearch.com/docs/getting-started/installation`
3. Open that exact URL rather than using a search engine or installing a standalone
   search provider.
4. If installation is needed, show the current official command and ask approval.
5. Do not request credentials in chat or use administrator privileges by default.

Current macOS, Linux, and WSL command shape:

```text
curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash
```

Current Windows PowerShell command shape:

```text
iex (irm https://hermes-agent.nousresearch.com/install.ps1)
```

## Configure

Use `hermes model` and `hermes tools`.

- From Codex, prefer OpenAI Codex with ChatGPT OAuth.
- From Claude, use Anthropic OAuth only when the subscription supports it.
- Detect supported reuse or import of the current Codex or Claude credential store
  first. Recommend that built-in import before recommending a separate login.
- Ask once for the exact system changes: install when needed, reuse or import the
  detected credential, connect the browser, install the user-level gateway, and
  register the confirmed outer folder as the active Hermes project and `terminal.cwd`.
- If approved, use the built-in credential flow without manually reading, printing, or
  copying tokens. Start a separate authentication flow only when no supported import is
  available, the user declines it, or it fails.
- Keep the local terminal backend.
- Enable browser, memory, session search, skills, and cron.
- Connect browser tools to local Google Chrome with `/browser connect`.
- Do not install a standalone search package.

Ask another question only when the approved path changes materially or a new
authentication flow requires user interaction.

If cron is enabled but the gateway is not running, show `hermes gateway install` and
ask before installing the user-level background service. Do not use a system service or
administrator privileges for this tutorial.

## Verify Without Handing Off

Run:

```text
hermes --version
hermes doctor
hermes tools
hermes gateway status
hermes cron status
```

Cron passes only when the user-level gateway is running. Do not create a scheduled job
merely to verify it.

## Point Hermes at the Workspace

Hermes installation and profile configuration live under its user-level home, not
inside the project. Register the confirmed outer folder as a Hermes project and make it
the active project without starting a chat.

Use current CLI help to confirm syntax. Current command shape:

```text
hermes project create "[WORKSPACE NAME]" "[OUTER PATH]" --primary "[OUTER PATH]" --use
hermes config set terminal.cwd "[OUTER PATH]"
```

If a Hermes project for that exact path already exists, reuse it instead of creating a
duplicate. Verify the active project and `terminal.cwd`.

This registration does not create `AGENTS.md`, `USER.md`, the wiki, or other
workspace-local files. The current Codex or Claude manager creates those files in Stage
3 from the starter. Both actions are part of initializing the workspace, but they have
different storage boundaries.

The current agent continues to Stage 3 from the confirmed outer workspace root. Do not
start a Hermes conversation merely to continue setup.
