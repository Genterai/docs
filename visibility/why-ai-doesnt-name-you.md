---
title: "Why doesn't ChatGPT mention my product?"
description: "The usual reasons an AI answer names a competitor and not you — crawlers shut out, a page missing from the search index, a question nobody watches — and how to check each one."
answers:
  - "Why doesn't ChatGPT mention my product when people ask about my category?"  # buyer-questions.md #1
facts:
  - claim: "On a site Genter serves, robots.txt lets search crawlers and AI crawlers in by default; only an explicit switch-off closes them."
    class: neutral
    source: "Genterai/specs specs/013-robots-and-crawl-reach FR-001, FR-004"
  - claim: "The AI crawlers Genter's robots.txt names include GPTBot, OAI-SearchBot, ChatGPT-User, ClaudeBot, PerplexityBot and Google-Extended."
    class: neutral
    source: "Genterai/app src/proxy.ts (AI_CRAWLERS)"
  - claim: "Google: to be shown as a supporting link in AI Overviews or AI Mode, a page must be indexed and eligible to be shown in Google Search with a snippet."
    class: neutral
    source: "https://developers.google.com/search/docs/appearance/ai-features (read 2026-09-30)"
  - claim: "Genter checks only the questions saved in the check; with none saved it checks nothing."
    class: neutral
    source: "Genterai/app src/lib/mentions/run.ts (No queries saved yet — nothing to check.)"
  - claim: "For each checked question Genter records the other sites on the results page and the sources of Google's AI Overview."
    class: neutral
    source: "Genterai/specs specs/119-mentions-checks FR-008, FR-011"
  - claim: "Genter's documentation has one page per buyer question, answered in the first paragraph."
    class: neutral
    source: "Genterai/docs CLAUDE.md (One page — one buyer question)"
---

# Why doesn't ChatGPT mention my product?

An AI answer names a product when its engine could read a page about it and chose that page over others for the question. When your product is missing, one of these links is usually broken. Check them in order.

## Can AI crawlers read your pages?

An engine cannot use a page its crawler was refused. `robots.txt` rules written against scrapers often block AI crawlers too — `GPTBot`, `OAI-SearchBot`, `ChatGPT-User`, `ClaudeBot`, `PerplexityBot`, `Google-Extended`.

Open `https://<your-site>/robots.txt` and look for a `Disallow: /` under any of these names.

On a site Genter serves, `robots.txt` lets search and AI crawlers in by default. Only an explicit switch-off by the owner closes them.

## Is the page in Google's index?

Google's AI Overviews and AI Mode cite pages from Google Search. Google says a page must be indexed and eligible to be shown with a snippet to appear there. A page Google has not indexed cannot be cited there, however good it is.

Search `site:` plus the page's address in Google to see whether it is indexed.

## Does one page answer the question?

A buyer asks "which tool does X?". If no page on your site answers that question in one place, the engine has nothing of yours to quote.

Genter's own docs follow this rule: one page per buyer question, answered in the first paragraph.

## Are you watching the question?

You only know what an engine answers for the questions someone checks. Genter checks only the questions saved in the check; a question nobody added is never asked, and its answer stays unknown. See [Which AI assistants does Genter check?](./which-ai-engines.md).

## Who gets named instead?

For each checked question Genter records the other sites on the results page and the sources Google's AI Overview cites. That list shows who the engine chose instead of you, and for which questions.

> Fixing these makes a page eligible to be cited. It does not make an engine name it: each engine decides on its own, and none publishes how.

## Related

<!-- widget:cards plain cols=2 -->

- [What are GEO and AEO?](./geo-vs-seo.md) {sparkles} {color:violet}
- [Why does the mention check show no data?](./check-shows-no-data.md) {circle-dashed} {color:gray}

<!-- /widget -->
