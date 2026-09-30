---
title: "What questions do people ask ChatGPT about my product?"
description: "No one outside OpenAI can see what people type into ChatGPT. Genter works out the likely questions, measures the search demand behind them, and reads what AI assistants actually answer."
answers:
  - "What questions do people ask ChatGPT about my product?"  # buyer-questions.md #7
facts:
  - claim: "The number of people who type a given prompt into ChatGPT is not available to Genter; the prompt demand figure is the search volume behind the searches a prompt turns into."
    class: neutral
    source: "Genterai/app src/components/analytics/geo/PromptDemandCard.tsx (HINT and header comment); src/lib/prompt-demand/run.ts"
  - claim: "For each prompt, Genter asks several AI models which searches the prompt turns into and measures the search volume of up to ten of them."
    class: neutral
    source: "Genterai/app src/lib/prompt-demand/run.ts (MAX_MEASURED_QUERIES, FANOUT_MODELS); src/lib/prompt-demand/cluster.ts"
  - claim: "Search volume is read for the project's region."
    class: neutral
    source: "Genterai/specs specs/080-search-data-reads-and-pricing FR-003"
  - claim: "Demand that was not measured is shown as empty, never as 0."
    class: neutral
    source: "Genterai/specs specs/251-upstream-method-and-project-model FR-010; specs/080-search-data-reads-and-pricing FR-001"
  - claim: "Genter can read what ChatGPT, Gemini, Perplexity, Copilot and Google's AI Mode answer to a prompt, and whether your site is cited."
    class: neutral
    source: "Genterai/specs specs/080-search-data-reads-and-pricing FR-005, FR-010"
  - claim: "Questions readers ask the assistant on your own site are recorded and grouped by wording."
    class: neutral
    source: "Genterai/specs specs/123-analytics-chat-insights FR-015"
---

# What questions do people ask ChatGPT about my product?

No one outside OpenAI can see what people type into ChatGPT, and Genter does not claim to. It gets close from three sides you can check:

<!-- widget:cards plain cols=3 -->

- [Which questions are likely](#which-questions-are-likely) — From your product and from where buyers already ask. {list-checks} {color:blue}
- [How many people ask them](#how-many-people-ask-them) — Prompt demand: the search demand behind a prompt. {chart-column} {color:green}
- [What ChatGPT answers](#what-does-chatgpt-answer) — The prompt put to the assistants, answer recorded. {message-square} {color:purple}

<!-- /widget -->

## Which questions are likely?

The ones your buyers need answered to choose, buy and use your product — "can it…", "how do I…", "how much…", "X or Y?". Genter works them out from what it knows about your product and from where buyers already ask: see [Where does Genter learn which questions my buyers ask?](./where-questions-come-from.md)

The questions readers type into the assistant on **your own site** are recorded directly, grouped by wording.

## How many people ask them?

Genter measures **prompt demand**: the search demand behind a prompt, not the number of people who type it. For each prompt it asks several AI models which searches the prompt turns into, and measures the search volume of up to ten of them, in your project's region.

<!-- widget:callout type=info -->

Demand that was not measured is shown as empty, never as `0` — an empty cell means "not known", not "nobody asks".

<!-- /widget -->

## What does ChatGPT answer?

Genter can put the prompt to ChatGPT, Gemini, Perplexity, Copilot and Google's AI Mode and record what each answers, and whether your site is cited. See [Which AI assistants does Genter check?](./which-ai-engines.md)

## Related

<!-- widget:cards plain cols=2 -->

- [Where does Genter learn which questions my buyers ask?](./where-questions-come-from.md) {search} {color:amber}
- [Why doesn't ChatGPT mention my product?](./why-ai-doesnt-name-you.md) {eye-off} {color:pink}

<!-- /widget -->
