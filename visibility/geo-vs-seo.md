---
title: "What are GEO and AEO, and how are they different from SEO?"
description: "SEO wins a place in a list of search results. GEO and AEO win a mention inside an answer an AI writes. What each term means, how each is measured, and where they overlap."
answers:
  - "What is GEO and AEO, and how is it different from SEO?"  # buyer-questions.md #4
facts:
  - claim: "Google: the best practices for SEO remain relevant for AI Overviews and AI Mode; there are no additional requirements to appear in them."
    class: neutral
    source: "https://developers.google.com/search/docs/appearance/ai-features (read 2026-09-30)"
  - claim: "Google: to be shown as a supporting link in AI Overviews or AI Mode, a page must be indexed and eligible to be shown in Google Search with a snippet."
    class: neutral
    source: "https://developers.google.com/search/docs/appearance/ai-features (read 2026-09-30)"
  - claim: "A search result has a rank and a count of results checked; an AI answer has no rank, only whether it names or cites you."
    class: neutral
    source: "Genterai/specs specs/119-mentions-checks FR-001, FR-010; Genterai/app src/components/analytics/mentions/MentionsPanel.tsx"
  - claim: "robots.txt names search crawlers and AI crawlers separately; Googlebot (search) and Google-Extended (Gemini, AI Overviews) are independent."
    class: neutral
    source: "Genterai/specs specs/013-robots-and-crawl-reach FR-003; Genterai/app src/proxy.ts"
---

# What are GEO and AEO, and how are they different from SEO?

**SEO** (search engine optimization) is work to rank in a search engine's list of results. **GEO** (generative engine optimization) and **AEO** (answer engine optimization) are two names for a newer goal: getting your product named, or your page cited, inside an answer an AI writes — in ChatGPT, Perplexity, Gemini, Copilot, or Google's AI Overview and AI Mode.

## What is different?

| | SEO | GEO / AEO |
|---|---|---|
| **What you win** | A position in a list of results | A mention or a citation inside one generated answer |
| **What you measure** | Your rank for a query, out of how many results | Whether the answer names or cites you for a question |
| **Where the number comes from** | The search results page | The answer the AI engine gives to that question |

A generated answer has no rank. An engine either names you or it does not, so a GEO number is a count of questions — "named in 3 of 12 watched questions" — not a position. Genter records both kinds the same way: a search result as "#4 of 10 results", an AI answer as "Cited in the AI answer" or "Not mentioned".

## Where do they overlap?

Most of the work is the same. Google says the best practices for SEO remain relevant for AI Overviews and AI Mode, with no additional requirements to appear in them. To be shown as a supporting link there, a page must be indexed and eligible to be shown in Google Search with a snippet.

A page that fails SEO basics — not indexed, blocked from crawling — cannot be cited by Google's AI features either.

## What does GEO add?

- **Doors for AI crawlers.** `robots.txt` addresses search crawlers and AI crawlers separately. `Googlebot` is search; `Google-Extended` is Gemini and AI Overviews; `GPTBot`, `OAI-SearchBot`, `ClaudeBot` and `PerplexityBot` are AI crawlers. A site can be open to one group and closed to the other.
- **Other engines.** ChatGPT, Perplexity and Copilot answer from their own sources, so ranking in Google does not tell you what they say.
- **Watching the questions.** No search console exists for AI answers: someone has to ask the engines the questions your buyers ask and record the answers. See [Which AI assistants does Genter check?](./which-ai-engines.md).

## Related

<!-- widget:cards plain cols=2 -->

- [Why doesn't ChatGPT mention my product?](./why-ai-doesnt-name-you.md) {eye-off} {color:pink}
- [Which AI assistants does Genter check?](./which-ai-engines.md) {radar} {color:cyan}

<!-- /widget -->
