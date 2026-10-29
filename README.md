# Better Neighbors MCP servers

Better Neighbors' four MCP servers, packaged for ChatGPT and Claude Code:

- **core**: podcasts, people, episodes, scanners, deep topics, clips and reports.
- **Youniverse**: the YouTube channel universe.
- **Clipix**: the clip review queue.
- **Moonshot**: American Moonshot's atlas.

Each server signs you in with your Google account, and Better Neighbors' access registry decides what you may use.
Installing the plugin grants no access: your Better Neighbors contact arranges it. Each server's address is in
[`plugins/better-neighbors/.mcp.json`](plugins/better-neighbors/.mcp.json).

## ChatGPT

In the ChatGPT desktop app, open **Plugins**, then **Add**, then **Add a marketplace**:

| Field | Value |
|---|---|
| Source | `https://github.com/BetterNeighborsAI/better-neighbors-plugin` |
| Git ref | `main` |
| Sparse paths | Leave empty |

Then **Add marketplace**, and **Install** beside Better Neighbors. ChatGPT opens Google's sign-in for each server: sign
in with your Google account each time. Use the plugin in a **Work** chat, and name the tool you want, for example *call
the ping tool of the Better Neighbors core MCP server*.

## Claude Code

```
/plugin marketplace add BetterNeighborsAI/better-neighbors-plugin
/plugin install better-neighbors@better-neighbors-mcp
```

Then run `/mcp`, select a server and sign in with Google in the browser that opens. Repeat for each server you use.

## Claude's apps: the desktop app and claude.ai

Add each server you need as a custom connector: **Settings**, **Connectors**, **+ Add**, **Add custom connector**,
with the server's name and its address, then **Connect** and sign in with Google.

## Check

Ask your assistant to run `ping` on a server: it answers who you are and what you may call.

This repository is generated from Better Neighbors' plugin marketplace: changes are made there and published here.
