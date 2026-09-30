---
title: "How many visitors am I losing because people ask AI instead of Google?"
description: "Genter does not estimate visitors lost to AI — nobody can observe the visit that never happened. It counts the visits AI assistants do send you and records whether their answers name you."
answers:
  - "How many visitors am I losing because people ask AI instead of Google?"  # buyer-questions.md #5
facts:
  - claim: "Genter has no metric for visitors lost to AI answers."
    class: neutral
    source: "Genterai/app src/utils/analytics/headline.ts, src/utils/analytics/breakdown.ts (no such measure)"
  - claim: "Visits that arrive from an AI assistant's answer are counted as their own channel, “AI assistant”."
    class: neutral
    source: "Genterai/app src/utils/analytics/traffic-source.ts (classifyTrafficSource); src/components/analytics/BreakdownCard.tsx"
  - claim: "The mention check records, per saved question, whether an AI answer names you, where you rank in search results, and who else appears."
    class: neutral
    source: "Genterai/specs specs/119-mentions-checks FR-001, FR-011"
  - claim: "A missing figure is shown as empty, never as 0."
    class: neutral
    source: "Genterai/app src/utils/analytics/headline.ts (nulls mean “cannot be said”)"
---

# How many visitors am I losing because people ask AI instead of Google?

Genter does not put a number on it. A visit that never happened leaves no trace on your site, so any "visitors lost" figure would be a guess, and Genter does not print guesses as measurements.

What Genter measures instead are the two sides you can see.

## How many visitors does AI send me?

Visits that arrive from an AI assistant's answer — ChatGPT, Perplexity, Claude, Copilot, Gemini — are counted as their own channel, **AI assistant**, next to organic search and direct. See [how that count works and why it is a floor](./found-through-chatgpt.md).

## Where does AI answer without me?

The **mention check** asks your buyers' saved questions to AI assistants and search engines every day and records:

- whether the AI answer names you
- where you rank in the search results
- who else is named or ranked instead

A question where the answer names a competitor and not you is the visitor you are not getting — named, not estimated.

## Related

- [Customers say they found us through ChatGPT — how do I check?](./found-through-chatgpt.md)
- [Why doesn't ChatGPT mention my product?](./why-ai-doesnt-name-you.md)
- [Which AI assistants does Genter check?](./which-ai-engines.md)
