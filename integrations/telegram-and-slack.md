---
title: "How do I answer Genter's questions from Telegram or Slack?"
description: "Connect a Telegram bot or your own Slack app, then reply to the bot's message, mention it, use /ask or write to it directly. A reply continues the agent's work, and the answer comes back to the same chat."
answers:
  - "How do I answer Genter's questions from Telegram or Slack?"  # buyer-questions.md #50
facts:
  - claim: "A Telegram bot is connected with its token from @BotFather (/newbot); the token is checked with Telegram before it is saved."
    class: neutral
    source: "Genterai/app src/lib/integrations/registry.ts (TELEGRAM_APP bot_token); Genterai/specs specs/101-chat-bots-telegram-slack User Story 2"
  - claim: "The Telegram bot acts only in chats on its allow-list; an empty list means no chat."
    class: neutral
    source: "Genterai/specs specs/101-chat-bots-telegram-slack FR-002"
  - claim: "In Telegram the bot reacts to a reply to its own message, a mention, the /ask command, and any message in a private chat."
    class: neutral
    source: "Genterai/specs specs/101-chat-bots-telegram-slack FR-001"
  - claim: "With Group Privacy on in BotFather (the default), a plain mention in a group does not reach the bot; /ask and replies to the bot still work."
    class: neutral
    source: "Genterai/specs specs/101-chat-bots-telegram-slack FR-004; Genterai/app src/lib/integrations/telegram/update.ts (telegramMentionsNote)"
  - claim: "To let the bot see mentions: in @BotFather open /mybots, the bot, Bot Settings, Group Privacy, Turn off, then remove the bot from the group and add it back."
    class: neutral
    source: "Genterai/app src/lib/integrations/telegram/update.ts (telegramMentionsNote)"
  - claim: "One Telegram bot has one webhook: connecting the same bot on two projects keeps the last connection."
    class: neutral
    source: "Genterai/specs specs/101-chat-bots-telegram-slack FR-005"
  - claim: "For Slack you create your own Slack app from a prefilled manifest, install it to your workspace and paste the Bot User OAuth Token and the Signing Secret."
    class: neutral
    source: "Genterai/app src/lib/integrations/registry.ts (SLACK_BOT setup and fields)"
  - claim: "After connecting, you paste the events address from the account card under Event Subscriptions in Slack; the card shows Listening once Slack has verified it."
    class: neutral
    source: "Genterai/app src/lib/integrations/slack/setup.ts; Genterai/specs specs/101-chat-bots-telegram-slack FR-009"
  - claim: "In Slack the bot reacts to mentions, direct messages and replies in a thread under its own messages; it joins a public channel itself, and a private channel needs /invite."
    class: neutral
    source: "Genterai/specs specs/101-chat-bots-telegram-slack FR-001; Genterai/app src/lib/integrations/registry.ts (SLACK_BOT chat_id)"
  - claim: "A reply to the agent's question while its run is open joins that run; after the run has finished, a new run starts with what was asked and answered."
    class: neutral
    source: "Genterai/specs specs/101-chat-bots-telegram-slack User Story 1"
  - claim: "A request from the chat runs on the project it names; otherwise on the project of the thread replied to, or the one opened last."
    class: neutral
    source: "Genterai/specs specs/101-chat-bots-telegram-slack FR-012"
  - claim: "The bot belongs to the organization, not to one project."
    class: neutral
    source: "Genterai/specs specs/101-chat-bots-telegram-slack (Overview); specs/099-integrations-catalog-and-accounts FR-009"
  - claim: "The answer in the chat is a few lines, business first."
    class: neutral
    source: "Genterai/specs specs/101-chat-bots-telegram-slack FR-007"
  - claim: "“Agent writes on its own” is on by default; it lets the agent post a question or news that needs a decision, with a link to the Inbox letter, and never a “task done” report. Off, the agent writes only to the Inbox and the bot still answers people who write to it."
    class: neutral
    source: "Genterai/app src/components/integrations/ConnectorDetailPage.tsx (AgentWritesSwitch); src/lib/integrations/agentOutbound.ts"
  - claim: "The agent posts only to chats and channels linked to the account."
    class: neutral
    source: "Genterai/specs specs/101-chat-bots-telegram-slack FR-010"
---

# How do I answer Genter's questions from Telegram or Slack?

Connect a bot once, then answer in the chat the way you would answer a colleague: reply to the bot's message. Your answer reaches the agent, and its answer comes back to the same chat.

## Connect Telegram

1. In Telegram, open **@BotFather**, send `/newbot` and copy the bot token.
2. In the panel, open **Integrations** → **Telegram** and paste the token. Genter checks it with Telegram before saving.
3. Add the bot to your chat. The bot acts only in chats on its **allow-list** — anyone can find a bot's username, so a chat that is not on the list gets an explanation and nothing else.

One bot token has one webhook: if you connect the same bot on two projects, the last connection wins.

### The bot doesn't react to @mentions in a group

Telegram's **Group Privacy** is on by default, and then a plain `@bot` mention in a group never reaches the bot. `/ask …` and replies to the bot's messages still work. To turn mentions on:

1. In **@BotFather**, open `/mybots` → your bot → **Bot Settings** → **Group Privacy** → **Turn off**.
2. Remove the bot from the group and add it back.

## Connect Slack

1. In **Integrations** → **Slack**, create your own Slack app from the prefilled manifest, pick your workspace and **Install to Workspace**.
2. Paste two values from the Slack app settings: the **Bot User OAuth Token** and the **Signing Secret**.
3. Copy the events address from the account card and paste it under **Event Subscriptions** in Slack. The card shows **Listening** once Slack has verified it.

The bot joins a public channel itself; a private channel needs `/invite @your-bot`.

## How do I answer?

| | Telegram | Slack |
|---|---|---|
| Reply to the bot's message | ✓ | ✓ (in the thread) |
| Mention the bot | ✓ (with Group Privacy off) | ✓ |
| `/ask …` | ✓ | — |
| Direct message | ✓ | ✓ |

- **While the agent is still working** on the task that asked, your reply joins that work.
- **After it has finished,** your reply starts a new run that is told what was asked and what you answered.

The answer in the chat is a few lines, business first.

A message that names a project runs on that project. Otherwise it runs on the project of the thread you replied to, or on the one you opened last. The bot belongs to your organization, not to one project.

## When does the agent write first?

When **Agent writes on its own** is on — the default — the agent posts to the linked chat when it has a question for you or news that needs your decision, with a link to the Inbox letter. It never posts a "task done" note. Turn it off and the agent writes only to the Inbox; the bot still answers anyone who writes to it.

The agent posts only to chats and channels linked to the account.

## Related

- [How much of my time does Genter take, and what will it ask me?](../getting-started/your-time-and-questions.md)
- [Integrations](./README.md)
