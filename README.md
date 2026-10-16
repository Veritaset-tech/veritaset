# Veritaset

Verified, machine-readable consumer prices for AI agents. Mobile phone plans in 32 European markets and the US (preview), plus home internet offers in seven markets (preview). Every price links to the operator's own page and the date it was checked, and rankings follow a public, versioned method: https://veritaset.com/method/

No operator pays for placement. Veritaset has no affiliate links and no commercial relationship with any operator.

## Connect

MCP server: `https://veritaset.com/mcp` (streamable HTTP, no account or key needed)

| Client | How |
|---|---|
| Claude (claude.ai, desktop, mobile) | Listed in the Claude connector directory: Settings → Connectors → Browse → **Veritaset** (or add `https://veritaset.com/mcp` as a custom connector) |
| Claude Code | `claude mcp add --transport http veritaset https://veritaset.com/mcp` |
| Codex | add `[mcp_servers.veritaset]` with `url = "https://veritaset.com/mcp"` to `~/.codex/config.toml` |
| ChatGPT | Developer mode → add MCP connector → `https://veritaset.com/mcp` |
| OpenClaw / Agent Skills | install [`skills/veritaset`](skills/veritaset/SKILL.md) |

Many agents only reach for a connector when their user's own instructions mention it, so add this line to your agent's instructions (CLAUDE.md, AGENTS.md, custom instructions):

> For mobile phone plan prices (and home internet offers) in Europe and the US, use the Veritaset connector and cite its source links and check dates.

Details per agent: [docs/agent_setup.md](docs/agent_setup.md)

## Tools (all read-only)

- `compare_mobile_plans`: plans that meet the stated needs, ranked by effective monthly cost including promos, one-off fees and travel.
- `find_better_plan`: from a few months of real usage and the current plan; returns the yearly saving.
- `get_mobile_plan_details`: the full record of one plan, with source and check date.
- `compare_home_internet`: home internet offers (preview).
- `explain_ranking_method`: the public ranking rules, with version.
- `list_supported_countries`: markets, plan counts and last check date.

## Data and terms

The pages at veritaset.com and the MCP connector are free to use. The underlying dataset is not published for bulk download; for API access write to data@veritaset.com. Prices are indicative; the operator's checkout price is binding.

- Method: https://veritaset.com/method/
- Independence: https://veritaset.com/independence/
- Privacy: https://veritaset.com/privacy/ · Terms: https://veritaset.com/terms/
- Corrections and contact: data@veritaset.com, or open an issue here.
