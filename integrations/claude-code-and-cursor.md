---
title: "How do I connect Genter to Claude Code or Cursor?"
description: "Copy the one-line command or config for your AI client from the panel, approve the connection once, and the assistant can read your project's docs and give tasks to the Genter agent. It cannot change settings, pages or people."
answers:
  - "How do I connect Genter to Claude Code or Cursor?"  # buyer-questions.md #46
facts:
  - claim: "In the panel, Connect ▸ MCP server shows the endpoint, the ready `claude mcp add` line for Claude Code and the JSON block for Cursor; any other MCP client takes the same endpoint."
    class: neutral
    source: "Genterai/app src/components/integrations/ConnectorDetailPage.tsx; src/lib/integrations/registry.ts (mcp)"
  - claim: "Claude Code connects with one `claude mcp add --transport http` command run in a terminal; Cursor takes a JSON block in ~/.cursor/mcp.json."
    class: neutral
    source: "Genterai/app src/components/integrations/ConnectorDetailPage.tsx"
  - claim: "On first use the client opens a Genter approval page; the connection works after you press Authorize."
    class: neutral
    source: "Genterai/specs specs/044-mcp-tokens-oauth-and-agent-keys FR-002, FR-004, FR-015"
  - claim: "The approval page lists what the client can do: read the docs of your projects, give tasks to the Genter agent where you can edit (billed to that project), and not change settings, pages or people."
    class: neutral
    source: "Genterai/app src/lib/mcp/consent.ts"
  - claim: "A connected client sees only reading and agent tools: project info, doc search and reading, the context pack, and starting, following, answering and stopping the Genter agent; it has no tools that write."
    class: neutral
    source: "Genterai/app src/lib/mcp/agent-surface.ts (OWNER_SURFACE); Genterai/specs specs/030-mcp-server-surfaces-and-audiences FR-003, SC-001"
  - claim: "A tool the connection may not use is not registered at all, so the client does not see it."
    class: neutral
    source: "Genterai/specs specs/030-mcp-server-surfaces-and-audiences FR-001"
  - claim: "Responses never include the project's secrets: its own model key, translation key, password hash or SSO client secret."
    class: neutral
    source: "Genterai/specs specs/030-mcp-server-surfaces-and-audiences FR-010"
---

# How do I connect Genter to Claude Code or Cursor?

In the panel open **Connect**, pick **MCP server**, copy the setup for your client from the card, and approve the connection once. After that your assistant can read your project's docs and hand work to the Genter agent.

## What do I paste where?

<!-- widget:tabs -->

### Claude Code {terminal}

Run the line from the card in a terminal. It has the form:

```bash
claude mcp add --transport http <name> <endpoint>
```

### Cursor {mouse-pointer}

Paste the JSON block from the card into `~/.cursor/mcp.json`. Merge it into the servers already listed there instead of replacing the file.

<!-- /widget -->

Any other MCP client — Codex CLI, Windsurf, Cline and the rest — takes the **Endpoint** from the same card.

## What happens on first use?

The client opens a Genter approval page. It names the client, the account it will act for, and your projects with your role in each. Press **Authorize** and go back to the assistant.

## What can the assistant do once connected?

| Can | Cannot |
|---|---|
| ✓ Search and read the docs of your projects | ✕ Change settings |
| ✓ Get a project's info and a context pack for a question | ✕ Edit or publish pages directly |
| ✓ Give a task to the Genter agent, follow it, answer its questions and stop it — in projects where you can edit; the task is billed to that project | ✕ Change people or access |

Tools the connection may not use are not offered to the client at all. Answers never include the project's secrets: its own model key, translation key, password hash or SSO client secret.

To change pages, ask the Genter agent through the assistant. The agent does the work, and you see it in the panel.

## Related

<!-- widget:cards plain cols=2 -->

- [Integrations](./README.md) {plug} {color:gray}
- [How do I answer Genter's questions from Telegram or Slack?](./telegram-and-slack.md) {message-circle} {color:sky}

<!-- /widget -->
