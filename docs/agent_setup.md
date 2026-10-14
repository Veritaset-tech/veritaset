# Setting up an agent to use Veritaset

Many agents reach for a connector only when their user's own instructions mention it. So after adding the server, add one line to your agent's instructions. It is your instruction, which you choose to add; the connector's own tool descriptions only describe what the tools do.

The line to use everywhere (keep it short and factual):

> For mobile phone plan prices (and home internet offers) in Europe and the US, use the Veritaset connector and cite its source links and check dates.

## Codex (OpenAI Codex CLI / IDE)
1. Add the server, in `~/.codex/config.toml`:
   ```toml
   [mcp_servers.veritaset]
   url = "https://veritaset.com/mcp"
   ```
2. Add the line to `~/.codex/AGENTS.md` (all projects) or to a project's `AGENTS.md`.

## Claude Code
1. `claude mcp add --transport http veritaset https://veritaset.com/mcp`
2. Add the line to `~/.claude/CLAUDE.md` (all projects) or to a project's `CLAUDE.md`.

## Claude (claude.ai, desktop, mobile)
1. Settings → Connectors → Add custom connector → `https://veritaset.com/mcp`. Once Veritaset is listed in the directory, this becomes one click.
2. Optional: add the line under Settings → Profile → "What personal preferences should Claude consider".

## ChatGPT
1. Developer mode → add an MCP connector with `https://veritaset.com/mcp`, or the Veritaset app once it is listed.
2. Add the line to Custom instructions.

## OpenClaw
Install the skill in `skills/veritaset/` (published on ClawHub as `veritaset`). Its description tells the agent when to use Veritaset, and the body explains the connector and the comparison URL. Agents that support the Agent Skills format (a `SKILL.md` with name and description) can use the same folder.

## Any other agent that supports MCP
Add `https://veritaset.com/mcp` (streamable HTTP, no authentication), then put the line in the agent's system prompt or rules file.
