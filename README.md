# Sekura plugins

Manifests that connect AI coding tools to the Sekura MCP server at `https://sekura.ai/mcp`.

Sekura scans a GitHub repository for vulnerabilities and delivers a report with proof for every finding; from your agent you can see your repositories, start a scan you have approved, read the findings, and manage a schedule.

This repository holds manifests only. Every one of them points at the same server, and nothing here runs on your machine: sign-in is OAuth 2.1 at the server (PKCE, Dynamic Client Registration, Client ID Metadata Documents), so no key is copied anywhere. The full guide for every tool, with the exact snippet or one-click link, is at https://sekura.ai/connect/.

## Install

| Tool | How |
|---|---|
| Claude Code | `/plugin marketplace add sekuraai/sekura-plugins`, then `/plugin install sekura@sekura`. Or without the plugin: `claude mcp add --transport http sekura https://sekura.ai/mcp` then `/mcp` to sign in |
| Claude (app and web) | Settings, Connectors, Add custom connector, address `https://sekura.ai/mcp` |
| Cursor | The one-click link on https://sekura.ai/connect/, or clone this repository into `~/.cursor/plugins/local/` (the plugin is this repository's root) |
| Kiro | Add Custom Power, Import power from GitHub, this repository |
| Antigravity | `antigravity/`: the manifest and `mcp_config.json`; or add `https://sekura.ai/mcp` as a custom server |
| VS Code, Copilot CLI, JetBrains, Zed, Codex, Devin, Replit, Lovable, Bolt, v0 and the rest | https://sekura.ai/connect/ |

## What is where

| Path | Venue |
|---|---|
| `.claude-plugin/marketplace.json`, `plugins/sekura/` | Claude Code plugin marketplace; the plugin's skill teaches the quote-then-confirm flow |
| `plugin.json`, `mcp.json` | Agent Plugins standard manifest at the root: Kiro Powers, Cursor |
| `.cursor-plugin/plugin.json` | Cursor Marketplace and cursor.directory |
| `registry/server.json` | The official MCP Registry entry, `ai.sekura/sekura`, published with `mcp-publisher` |
| `docker/servers/sekura/` | The Docker MCP Catalog entry, submitted as a pull request to docker/mcp-registry |
| `cline/` | The Cline marketplace listing: README, `llms-install.md`, 400 by 400 logo |
| `antigravity/` | Google Antigravity plugin manifest and MCP configuration |
| `gemini/gemini-extension.json` | Gemini CLI extension (legacy gallery) |
| `logo.png` | The Sekura owl, 512 by 512 |

## How the server behaves

Read tools are free and need no confirmation. Every write tool (start a scan, start a recurring plan, run a plan now, cancel) answers first with a preview that names the repository, the authorization wording and the price, and runs only when called again with the arguments the preview names, after the user has agreed in the conversation. A card is charged only after the user approves the quoted amount; otherwise the answer carries a Stripe Checkout link.

Privacy: https://sekura.ai/privacy/. Terms: https://sekura.ai/terms/. Support: hello@sekura.ai.
