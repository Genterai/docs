---
title: "Genter — your agent to enter the market"
description: "Genter is your agent to enter the market. It learns your product, answers your buyers' questions where they ask — ChatGPT, Claude, Google — and proves what worked."
layout: landing
facts:
  - claim: "Genter — your agent to enter the market; it learns your product, answers your buyers' questions where they ask and proves what worked."
    class: neutral
    source: "Genterai/specs decisions/0006-answers-vs-documentation-wording.md"
  - claim: "The field on the home page takes your site's address; after sign-in Genter creates a project from it and runs the audit there."
    class: neutral
    source: "Genterai/specs decisions/0016-audit-lives-in-issues-no-report-page.md"
  - claim: "The audit works out the questions buyers ask and whether AI answers name the product or who they name instead."
    class: neutral
    source: "Genterai/specs decisions/0016-audit-lives-in-issues-no-report-page.md (item 5), visibility/what-buyers-ask-ai.md"
  - claim: "The agent writes pages from your own sources; prices, plans and contacts come only from what it saw there."
    class: neutral
    source: "Genterai/specs specs/170-anon-draft-generation/spec.md (overview)"
  - claim: "Every change Genter makes to your pages is a pull request; the review mode decides whether it merges at once or waits for you."
    class: neutral
    source: "publishing/does-genter-publish-on-its-own.md"
  - claim: "When the data cannot carry a figure, Genter says Can't tell and names why."
    class: neutral
    source: "results/cant-tell.md, Genterai/specs specs/255-product-model/spec.md FR-028"
  - claim: "Plans and prices are on /pricing."
    class: neutral
    source: "Genterai/app src/app/pricing/page.tsx (GEN-99)"
---

<!-- widget:cta start hero -->

# Genter — your agent to enter the market

Genter learns your product, answers your buyers' questions where they ask — ChatGPT, Claude, Google — and proves what worked.

- Paste your website address…
- Does ChatGPT name your product?
- Who do AI answers name instead of you?

Already know what you need? [See plans and pricing](/pricing).

[Check my site](/report)

<!-- /widget -->

## What your brand gets

<!-- widget:cards plain cols=3 -->

- [The questions buyers ask](./visibility/what-buyers-ask-ai.md) — Genter works out what buyers ask AI about your category and checks whether the answers name you, or who they name instead. {message-circle-question}
- [Pages that answer them](./publishing/does-genter-publish-on-its-own.md) — The agent writes the pages from your own sources. Every change is a pull request: it merges at once or waits for you — you choose. {git-pull-request}
- [Proof, or "can't tell"](./results/cant-tell.md) — Genter reports what changed after a page went live, and says **Can't tell** when the data is too thin to say. {chart-line}

<!-- /widget -->

These docs answer the questions buyers ask about Genter, in their own words. Each page starts from one question and answers it on the page itself.

## Sections

<!-- widget:cards feature cols=3 -->

- [Getting started](./getting-started/README.md) — What you need to start, and what Genter will ask of you. {rocket} {color:green}
- [AI and search visibility](./visibility/README.md) — Whether AI assistants and search engines name your product, and why they don't. {radar} {color:purple}
- [Publishing](./publishing/README.md) — How Genter writes pages, how they go live and how they stay current. {git-pull-request} {color:blue}
- [Your site](./site/README.md) — Languages, regions, and docs you already have elsewhere. {globe} {color:sky}
- [Results](./results/README.md) — Leads, sales, and when the data is too thin to say. {target} {color:amber}
- [Integrations](./integrations/README.md) — What Genter connects to, and in which direction data flows. {plug} {color:pink}

<!-- /widget -->

## How to read these pages

<!-- widget:callout type=info -->

Every page lists, in its frontmatter, the questions it answers (`answers`) and the facts it stands on (`facts`), each with its source. A page states only what its sources show. When something is not built yet, the page says so instead of promising it.

<!-- /widget -->
