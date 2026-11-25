# Agent C for Claude Code

[Agent C](https://agentc.croutons.ai) finds what keeps a small business out of AI answers and writes the fix. This plugin lets Claude Code read those fixes and make them in your website's code. Nothing goes live: every change waits for you to review.

## Install

```bash
claude plugin marketplace add malwarescan/agent-c-plugin
```

```bash
claude plugin install agent-c@agent-c
```

Then, in Claude Code, run `/mcp`, pick **agent-c** and sign in with the email on your Agent C account. Pick your website and tap **Allow**.

If you added Agent C before with `claude mcp add`, remove that copy so Claude doesn't see the tools twice:

```bash
claude mcp remove --scope user agent-c
```

## Use

Open your website's folder in Claude Code and ask:

> Apply the Agent C fixes in this repo.

Or type a command:

- `/agent-c:apply-fixes` works through every open fix. Add a fix's title or number to do just one.
- `/agent-c:ai-visibility` says how often AI assistants name you and who they name instead. Add `recheck` to run a fresh check (at most once an hour).

## What it includes

- The hosted Agent C MCP server, `https://api.croutons.ai/mcp` (tools `list_fixes`, `get_fix`, `visibility_status`, `recheck`).
- Two skills, `apply-fixes` and `ai-visibility`, that tell Claude how to use them: find the right file, keep your wording, ask about placeholders, never publish.

## What it sends

The plugin runs no code on your computer. It only connects Claude Code to Agent C's MCP server at `https://api.croutons.ai/mcp`, which you sign in to yourself. It sends Agent C nothing from your repository: Claude reads fixes from Agent C and makes the changes locally.

Claude can read the fixes for the one site you picked and start a check. It can't approve, publish or change anything in your Agent C account. To cut it off, open **Connections**, then **Coding agents** in the Agent C app and tap **Disconnect**.

## License

MIT. The plugin files only; the Agent C service has its own terms at https://agentc.croutons.ai.
