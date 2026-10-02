---
title: "Which AI assistants does Genter check?"
description: "Genter asks your buyers' questions to ChatGPT, Gemini, Perplexity, Copilot and Google's AI Overview and AI Mode, and reads Google, Bing, Yandex, YouTube and Amazon results. Claude is not checked."
answers:
  - "How do I find out what ChatGPT, Perplexity and Google AI say about my company?"  # buyer-questions.md #2
  - "Which AI assistants does Genter check?"  # buyer-questions.md #18
facts:
  - claim: "Genter can read answers from ChatGPT, Gemini, Perplexity, Google AI Mode and Copilot, Google results with the AI Overview, and Bing, Yandex, YouTube and Amazon results."
    class: neutral
    source: "Genterai/specs specs/080-search-data-reads-and-pricing FR-005"
  - claim: "Genter does not read Claude, Yahoo, Baidu or Grok."
    class: neutral
    source: "Genterai/specs specs/080-search-data-reads-and-pricing FR-005; decisions/0006 (Consequences)"
  - claim: "How many questions the daily check watches, and which engines it asks, depends on the plan."
    class: neutral
    source: "Genterai/specs specs/119-mentions-checks FR-014"
  - claim: "Questions are checked in the project's region, set as a two-letter country code."
    class: neutral
    source: "Genterai/specs specs/080-search-data-reads-and-pricing FR-003; specs/119-mentions-checks FR-012"
  - claim: "An AI answer is recorded as “Cited in the AI answer”, “Ranks below the AI answer” or “Not mentioned”; a search result as a position out of the results checked."
    class: neutral
    source: "Genterai/app src/components/analytics/mentions/MentionsPanel.tsx (verdictLine)"
  - claim: "Each check keeps earlier readings of the same question, so you see where you stood over time."
    class: neutral
    source: "Genterai/specs specs/119-mentions-checks FR-004"
---

# Which AI assistants does Genter check?

Genter asks your buyers' questions to AI assistants and search engines and records whether the answer names you. It reads:

- **AI answers:** ChatGPT, Gemini, Perplexity, Copilot, Google's AI Mode, and the AI Overview at the top of Google results
- **Search results:** Google, Bing, Yandex, YouTube and Amazon

Claude, Yahoo, Baidu and Grok are not checked. Genter does not offer an engine it cannot read.

## How do I find out what they say about my company?

Save the questions your buyers ask — "best tool for X", "X vs Y", "how do I do Z" — in the mention check. Genter asks each of them every day, in your project's region, and records one line per question and engine:

| Engine | What you see |
|---|---|
| AI answer | `Cited in the AI answer`, `Ranks below the AI answer` or `Not mentioned` |
| Search results | `#4 of 10 results`, or `Not in the top 10` — and which other sites on that page name you |

Earlier readings of the same question are kept, so you see where you stood over time, not only today.

How many questions the daily check watches, and which of these engines it asks, depends on your plan.

## What can't these checks tell you?

- **Questions nobody saved.** Genter asks only the questions in the check.
- **Other regions.** Answers differ by country; each project is checked in its own region.
- **Claude.** It is not read.

## Related

<!-- widget:cards plain cols=2 -->

- [Why doesn't ChatGPT mention my product?](./why-ai-doesnt-name-you.md) {eye-off}
- [Why does the mention check show no data?](./check-shows-no-data.md) {circle-dashed}

<!-- /widget -->
