# Make Demo Plugins

A small marketplace used to demo **Plugins in Make AI Agents**: a catalog of plugins, each a pack
of skills and MCP servers an agent can be given in one install.

## Use it

In Make: **AI Agents → Plugins → Marketplaces → Register**, and paste this repository's URL.
Then install **Research Desk** and attach it to an agent.

## What's in it

### Research Desk

| | |
| --- | --- |
| `research-brief` | a skill: "brief me on X" runs a fixed three-search procedure and writes five fixed sections |
| `investigate-repo` | a skill: what a public GitHub repository is and how it is built |
| `tavily` | MCP server, **needs a connection** — a free API key from [tavily.com](https://tavily.com) |
| `deepwiki` | MCP server, **needs nothing** — public, no account |

Two servers on purpose: one of each connection state, side by side in the scenario module.

`commands/` is a Claude Code slash command. Make has nothing to map it onto, so the preview lists
it as unsupported — that is expected, and everything else installs normally.

## Layout

```
.claude-plugin/marketplace.json     the catalog
plugins/research-desk/              the plugin, resolved via metadata.pluginRoot
```

The catalog follows the Claude Code marketplace format. Make also reads
`.cursor-plugin/marketplace.json` and `.agents/plugins/marketplace.json`.
