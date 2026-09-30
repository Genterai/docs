---
title: "Where does Genter learn which questions my buyers ask?"
description: "From your own readers (questions to the site assistant, failed searches, negative feedback), from search demand, from a model of your product, and from support and sales tools you connect."
answers:
  - "Where does Genter know which questions my buyers ask from?"  # buyer-questions.md #34
facts:
  - claim: "Questions readers ask the assistant on your site are recorded and identical wordings are grouped, with how many went unanswered."
    class: neutral
    source: "Genterai/specs specs/123-analytics-chat-insights FR-015"
  - claim: "Each assistant conversation is classified by intent — evaluation, pricing, integration, problem, bug or other — and by whether the pages answered it fully, partly or not at all."
    class: neutral
    source: "Genterai/specs specs/123-analytics-chat-insights FR-019"
  - claim: "Unanswered assistant questions, failed on-site searches and negative feedback on pages are ranked together to show what to fix first."
    class: neutral
    source: "Genterai/specs specs/121-analytics-visits-headline FR-015, FR-016"
  - claim: "Genter can measure the search demand behind a question, in the project's region."
    class: neutral
    source: "Genterai/app src/lib/prompt-demand/run.ts; Genterai/specs specs/080-search-data-reads-and-pricing FR-003"
  - claim: "On request, the agent builds a model of the product from its sources and turns what the product can and cannot do into buyer questions — can, how, limit, fail, cost, choose — checked against the existing pages."
    class: neutral
    source: "Genterai/specs specs/251-upstream-method-and-project-model User Story 1, User Story 2, FR-009"
  - claim: "Intercom, Zendesk and HubSpot connections read support conversations and tickets, help articles, and sales notes and contacts."
    class: neutral
    source: "Genterai/app src/lib/integrations/registry.ts (INTERCOM_APP, ZENDESK_APP, HUBSPOT_APP tools)"
  - claim: "Genter does not read what people type into ChatGPT."
    class: neutral
    source: "Genterai/app src/components/analytics/geo/PromptDemandCard.tsx (header comment)"
---

# Where does Genter learn which questions my buyers ask?

From four places. None of them is ChatGPT's own log: what people type there is not visible to anyone outside OpenAI.

## 1. Your own readers

- **The assistant on your site.** Every question readers ask it is recorded; identical wordings are grouped, with how many went unanswered — for example, "asked 11 times, 9 unanswered".
- **What kind of question it was.** Each conversation is classified by intent — evaluation, pricing, integration, problem, bug — and by whether your pages answered it fully, partly or not at all.
- **What readers could not find.** Unanswered questions, searches on your site that found nothing, and negative feedback on pages are ranked together, so the gap readers hit most comes first.

## 2. Search demand

For a question, Genter measures the search demand behind it in your project's region. See [What questions do people ask ChatGPT about my product?](./what-buyers-ask-ai.md)

## 3. Your product

When you ask the agent to work out your buyers' questions, it builds a model of your product from its sources — code, pages, your description — and turns what the product can and cannot do into the questions a buyer asks: *can it*, *how do I*, *what are the limits*, *why doesn't it work*, *how much*, *which to choose*. Each question is checked against the pages you already have.

What the sources don't show, it asks you instead of guessing.

## 4. Support and sales tools you connect

| Tool | What Genter reads |
|---|---|
| Intercom | Support conversations and help articles |
| Zendesk | Tickets and help articles |
| HubSpot | Call notes and emails on deals, and contacts |

These are the questions your team already answers one by one, which a page could answer once.

## Related

- [What questions do people ask ChatGPT about my product?](./what-buyers-ask-ai.md)
- [How much of my time does it take, and what will Genter ask me?](../getting-started/your-time-and-questions.md)
- [Can leads from my pages go to HubSpot or another CRM?](../integrations/crm.md)
