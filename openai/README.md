# Sekura for ChatGPT and Codex

The plugin source for OpenAI's plugin directory, shared by ChatGPT and Codex.
It is uploaded as a ZIP of this folder at https://platform.openai.com/plugins,
through Create plugin, With MCP.

| File | What it is |
|---|---|
| `plugin.json` | The Agent Plugins manifest, with the listing under `extensions["com.openai"].interface` |
| `mcp.json` | One remote server, `https://sekura.ai/mcp/community`, signed in by OAuth with a Client ID Metadata Document (DCR remains the fallback) |
| `assets/logo.png` | The Sekura owl, 512 by 512, the listing logo |
| `assets/icon.png` | The Sekura owl, 128 by 128, the composer icon |

## Why this plugin points at `/mcp/community`

Every other manifest in this repository names `https://sekura.ai/mcp`. This one
does not, because OpenAI's directory does not allow selling inside a listed
plugin. The community address is the same server and the same sign-in, with
every read, the cancels and schedule changes. It starts no scan or plan and
never offers a paid action; asked for one, it answers with a sentence pointing
to sekura.ai, where scans and plans are started.

People who connect Codex by hand (`codex mcp add sekura --url https://sekura.ai/mcp`)
get the full set; that path is documented at
https://sekura.ai/connect/#tools-codex and is not this plugin.

## Building the upload

From this folder: `zip -r -X ../sekura-openai-plugin.zip plugin.json mcp.json assets LICENSE`.
This README stays out of the ZIP.

The submission also needs the domain challenge at
`https://sekura.ai/.well-known/openai-apps-challenge`, five positive and three
negative test cases, a walkthrough video and a demo account, all entered in
the portal, never in the ZIP.

## Contact

Support: support@sekura.ai, https://sekura.ai/contact/. Privacy:
https://sekura.ai/privacy/. Terms: https://sekura.ai/terms/.

## Licence

MIT; see `LICENSE`.
