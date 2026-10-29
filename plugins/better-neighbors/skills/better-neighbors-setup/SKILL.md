---
name: better-neighbors-setup
description: Sets up Better Neighbors' four MCP servers (core, Youniverse, Clipix and Moonshot) in the app it runs in, Claude Code or the ChatGPT desktop app, the same way in both - each server added with the app's own command and the person's approval, a Google sign-in for each, then a new chat. Use when the user asks to set up, install, connect or add the Better Neighbors servers or MCP servers, or says core, Youniverse, Clipix or Moonshot tools are missing.
---

# Set up the Better Neighbors servers

The servers are added to the app directly, one command per server, the same way in Claude Code and in ChatGPT. This
plugin carries no servers of its own: ChatGPT shows only the first 64 KB of a plugin's tools, which our servers far
exceed, and one plugin serves both apps.

## The servers

| name | address |
|---|---|
| `core` | `https://core-mcp-352866389133.us-central1.run.app/mcp` |
| `youniverse` | `https://youniverse-mcp-352866389133.us-central1.run.app/mcp` |
| `clipix` | `https://clipix-mcp-352866389133.us-central1.run.app/mcp` |
| `moonshot` | `https://america-moonshot-mcp-352866389133.us-central1.run.app/mcp` |

Add the ones the person asks for, or all four when they don't say. Signing in grants nothing by itself: each server
asks Better Neighbors' access registry what the person may use, so a server that refuses them means they hold no
access there yet; their Better Neighbors contact arranges it.

## Steps

The commands differ by app; the steps do not. In ChatGPT, run `codex` as
`/Applications/ChatGPT.app/Contents/Resources/codex-cli/bin/codex` when it is not on the PATH.

1. **See what is already there**: `claude mcp list` in Claude Code, `codex mcp list` in ChatGPT. A server already
   listed with its address is done; skip it. In Claude Code, servers that come from the core-systems plugin show as
   `plugin:core-systems:NAME`: the person already has them, so say so and add nothing.
2. **Add each missing server**, showing the command and running it once the person approves:
   - Claude Code: `claude mcp add --transport http --scope user NAME ADDRESS`
   - ChatGPT: `codex mcp add NAME --url ADDRESS`
3. **ChatGPT only, once**: `codex features enable code_mode_tool_search`, so ChatGPT finds the servers' few hundred
   tools by searching when it needs them instead of loading them all.
4. **Sign in** with the person's own Google account, one server at a time:
   - Claude Code: the person runs `/mcp`, selects each new server and signs in in the browser that opens.
   - ChatGPT: `codex mcp add` opened the sign-in already. A server that `codex mcp list` shows as `Not logged in`
     gets `codex mcp login NAME`; it happens after a ChatGPT update.
5. **Open a new chat** (a new Work chat in ChatGPT): the servers appear there, with no restart. Then ask for the
   `ping` tool of the core server: it answers who the person is and what they may call.

## Without a terminal

Claude's desktop app and claude.ai cannot run these commands. There the person adds each server as a custom
connector: Settings, Connectors, + Add, Add custom connector, with the name and the address above, then Connect and
the Google sign-in. A connector added in one shows in the other.
