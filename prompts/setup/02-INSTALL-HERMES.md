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
2. Read the current official installation page:
   `https://hermes-agent.nousresearch.com/docs/getting-started/installation`
3. If installation is needed, show the current official command and ask approval.
4. Do not request credentials in chat or use administrator privileges by default.

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
- When Hermes offers its supported reuse or import of the current agent's credential
  store, show that choice and ask approval. If approved, use the built-in flow without
  manually reading, printing, or copying tokens.
- Keep the local terminal backend.
- Enable browser, memory, session search, skills, and cron.
- Connect browser tools to local Google Chrome with `/browser connect`.
- Do not install a standalone search package.

Ask before reusing credentials or starting a new authentication flow.

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

The current agent continues to Stage 3 from the confirmed outer workspace root. Do not
start a Hermes conversation merely to continue setup.
