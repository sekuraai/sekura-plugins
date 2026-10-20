# Installing the Sekura MCP server in Cline

Sekura is a remote MCP server. Nothing is installed locally.

1. Open Cline settings, then MCP Servers, then the Remote Servers tab.
2. Server name: `sekura`. Server URL: `https://sekura.ai/mcp`.
3. Save. Cline opens Sekura's OAuth sign-in page in the browser: sign in with GitHub, check the account named, and choose Approve.
4. Back in Cline, the `sekura` server lists its tools. Call `getAccount` to confirm the sign-in.

Every scan and plan takes two calls: the first answers with a preview and the price, the second, with the arguments the preview names, runs it. Show the preview to the user and wait for their agreement before the second call.

Documentation: https://sekura.ai/connect/
