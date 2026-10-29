# Better Neighbors MCP servers

Better Neighbors' four MCP servers:

- **core**: podcasts, people, episodes, scanners, deep topics, clips and reports.
- **Youniverse**: the YouTube channel universe.
- **Clipix**: the clip review queue.
- **Moonshot**: American Moonshot's atlas.

Each server signs you in with your Google account, and Better Neighbors' access registry decides what you may use.
Installing grants no access: your Better Neighbors contact arranges it.

The **Better Neighbors** plugin sets the servers up the same way in ChatGPT and in Claude Code: install it, ask it to
*set up the Better Neighbors servers*, approve the commands it shows, sign in with Google for each server, then open
a new chat. The plugin carries no servers itself, because ChatGPT shows only the first 64 KB of a plugin's tools;
each server's address is in
[`plugins/better-neighbors/skills/better-neighbors-setup/SKILL.md`](plugins/better-neighbors/skills/better-neighbors-setup/SKILL.md).

## ChatGPT (the desktop app)

1. Open **Plugins**, then **Add**, then **Add a marketplace**:

   | Field | Value |
   |---|---|
   | Source | `https://github.com/BetterNeighborsAI/better-neighbors-plugin` |
   | Git ref | `main` |
   | Sparse paths | Leave empty |

2. **Add marketplace**, then **Install** beside Better Neighbors.
3. In a **Work** chat, ask *set up the Better Neighbors servers*. Approve each command, and sign in with your Google
   account in the browser for each server.
4. Open a new **Work** chat and ask for the ping tool of the core server.

## Claude Code

```
/plugin marketplace add BetterNeighborsAI/better-neighbors-plugin
/plugin install better-neighbors@better-neighbors-mcp
```

Then ask Claude to *set up the Better Neighbors servers*, approve each command, run `/mcp` to sign in to each
server, and ask for the ping tool of the core server.

## Claude's apps: the desktop app and claude.ai

They cannot run commands, so add each server as a custom connector: **Settings**, **Connectors**, **+ Add**, **Add
custom connector**, with the server's name and its address, then **Connect** and sign in with Google.

## Check

Ask your assistant to run `ping` on a server: it answers who you are and what you may call.

This repository is generated from Better Neighbors' plugin marketplace: changes are made there and published here.
