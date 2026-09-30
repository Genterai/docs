---
title: "How much of my time does Genter take, and what will it ask me?"
description: "Genter works on its own and writes to you only with a report worth reading or a question it cannot settle without you. A question is one letter you can answer in a sentence — from the Inbox, the chat, Telegram or Slack."
answers:
  - "How much of my time does it take, and what will Genter ask me about?"  # buyer-questions.md #31
facts:
  - claim: "The agent writes a letter to the Inbox only for a report worth a person's reading or a question it cannot decide without the owner; a run that finishes well writes nothing."
    class: neutral
    source: "Genterai/specs specs/160-inbox-letters FR-003; Genterai/app src/lib/mcp/server-factory.ts (send_inbox_message)"
  - claim: "A question is a letter that ends in a plain question, asked so it can be answered in a sentence."
    class: neutral
    source: "Genterai/app src/lib/mcp/server-factory.ts (send_inbox_message)"
  - claim: "The agent does not stop to wait for the answer and does not ask again just because a question is still unanswered."
    class: neutral
    source: "Genterai/app src/lib/mcp/server-factory.ts (send_inbox_message)"
  - claim: "The report of the first documentation run lists what could not be confirmed as at most five short questions."
    class: neutral
    source: "Genterai/app src/lib/automations/intent-catalog.ts (docs-from-site and docs-from-brief report)"
  - claim: "A question can be answered from the Inbox, from the chat in the panel, or from a linked Telegram or Slack chat."
    class: neutral
    source: "Genterai/specs specs/101-chat-bots-telegram-slack User Story 1; Genterai/app src/lib/mcp/server-factory.ts (send_inbox_message)"
  - claim: "A letter is short Markdown and can carry cards for the records it is about — phrases, issues, pull requests."
    class: neutral
    source: "Genterai/specs specs/160-inbox-letters FR-001, FR-013"
---

# How much of my time does Genter take, and what will it ask me?

As little as the work allows. Genter works on its own and writes to you only when it has something you need to read or a question only you can answer. A run that goes well writes nothing.

## What will I receive?

Letters in the **Inbox**, of two kinds:

| Letter | When |
|---|---|
| **Report** | Something happened that is worth your reading |
| **Question** | The agent needs a decision it cannot make from your code, pages or data |

A letter is short and can carry cards for the records it is about — a phrase, an issue, a pull request — so you open the thing itself, not a description of it.

## What kind of questions?

The ones only you can answer — what your product costs, what you promise customers, which of two readings of your product is right. A question is asked plainly enough to answer in a sentence.

After the first run that writes your pages, the report lists what the agent could not confirm as at most five short questions.

## Do I have to answer right away?

No. The agent does not stop and wait, and it does not ask again just because a question is still open. It carries on with the work that does not depend on your answer.

## Where do I answer?

Wherever is easiest:

- in the **Inbox**, by replying to the letter
- in the **chat** in the panel
- in a linked **Telegram** or **Slack** chat — see [How do I answer Genter's questions from Telegram or Slack?](../integrations/telegram-and-slack.md)

## Related

- [Does Genter publish on its own, or does everything wait for my approval?](../publishing/does-genter-publish-on-its-own.md)
- [How do I answer Genter's questions from Telegram or Slack?](../integrations/telegram-and-slack.md)
