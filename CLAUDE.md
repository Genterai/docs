# Genter documentation — how pages are written

This repository is the public documentation of Genter (`Genterai/specs` `decisions/0010`). Docsbook is an old project and only a reference: its pages are not copied, its name is not used as the product name, and links to its site or panel are not used.

## One page — one buyer question

- A page starts from a question in `Genterai/specs` `product/buyer-questions.md` and answers it in the buyer's words.
- The title is the question, or close to it. The first paragraph answers it.
- Brand line: "Genter — your agent to enter the market" (`decisions/0006`). The site is called "Docs".
- Write in English. Short paragraphs, identifiers in `code`, one question per section heading.

## Frontmatter: `answers` and `facts`

Every answer page carries (`specs/255` FR-023):

```yaml
---
title: "Why does the mention check show no data?"
description: "One sentence for search results."
answers:
  - "Why does the mention check show “no data”?"   # buyer question, as in buyer-questions.md
facts:
  - claim: "A switched-off check checks nothing."
    class: neutral            # neutral | commercial | promise | comparative | legal
    source: "Genterai/app src/lib/mentions/run.ts"
---
```

- `answers` — the questions the page closes, word for word from `product/buyer-questions.md`.
- `facts` — every claim the page makes, with its class (`specs/255` FR-006) and the source it was read from: a file in `Genterai/app` or `Genterai/specs`, or a public URL with the date it was read.

## Risk policy (`specs/255` FR-024, `decisions/0004`)

- `neutral` — publish when the source shows it.
- `commercial` (prices, plans, discounts, terms, contacts) — only the exact value from an owner source (for prices: `decisions/0009`).
- `promise` (guarantees, SLA, results, security and compliance, named customers, logos, reviews, cases) and `legal` — only when the owner has confirmed it.
- `comparative` — a factual comparison (price, feature, limit) only with a link to the competitor's public page read within 30 days; an evaluative one ("better", "faster") only when confirmed by the owner.
- In doubt, use the stricter class. A claim that fails the policy is left out; if the page no longer answers its question without it, the page waits.

## Publishing

Every change goes through a pull request (`specs/255` FR-025). The owner reviews and merges.
