---
title: "Can I see how many sales the pages brought?"
description: "As an estimate, not as orders. Genter counts visits that click through to your call-to-action link and multiplies them by an average price you set. Goals can carry their own value. Genter does not import real orders."
answers:
  - "Can I see how many sales the pages brought?"  # buyer-questions.md #36
facts:
  - claim: "Revenue is estimated as conversions times your average product price, where a conversion is a visit that clicks through to the host of your call-to-action link."
    class: neutral
    source: "Genterai/specs specs/121-analytics-visits-headline FR-008; Genterai/app src/utils/analytics/headline.ts"
  - claim: "Revenue stays empty until both the call-to-action link and the average price are set, and the panel says which one is missing."
    class: neutral
    source: "Genterai/specs specs/121-analytics-visits-headline FR-008; Genterai/app src/components/analytics/BreakdownCard.tsx (revenueBlockedBy hints)"
  - claim: "www.acme.com counts as acme.com, but docs.acme.com does not, so a return to your own docs is not counted as a sale."
    class: neutral
    source: "Genterai/specs specs/121-analytics-visits-headline FR-008"
  - claim: "A goal can carry a value; its value is completions times that value, counted once per visit, and a goal without a value is not treated as worth zero."
    class: neutral
    source: "Genterai/specs specs/122-analytics-goals-funnels-readers FR-003"
  - claim: "A reader's “potential” is a share of your average price based on how closely their visit resembles past converters; it is a ranking of intent, not a forecast of money."
    class: neutral
    source: "Genterai/specs specs/122-analytics-goals-funnels-readers FR-011; Genterai/app src/components/analytics/goals/shared.tsx"
  - claim: "No Genter connector imports orders or sends conversions to a CRM or billing system."
    class: neutral
    source: "Genterai/app src/lib/integrations/registry.ts (HubSpot sends nothing; no billing or sales-system connector)"
---

# Can I see how many sales the pages brought?

Yes — as an **estimate**, not as a count of orders. Genter does not see your payments. It counts the step before the sale on your pages and puts your price on it.

## How is the revenue figure made?

From two settings you give it:

<!-- widget:cards plain cols=2 -->

- A call-to-action link {link}

  Where a buyer goes to sign up or buy, for example `app.acme.com/signup`.

- An average product price {tag}

  What one sale is worth to you on average.

<!-- /widget -->

A visit that clicks through to that link's host counts as a **conversion**.

<!-- widget:callout type=note -->

**Revenue = conversions × your average price.**

<!-- /widget -->

Until both settings are there, revenue stays empty — not `$0` — and the panel says which one is missing: "Set an average product price" or "Set a CTA URL".

`www.acme.com` counts as `acme.com`, but `docs.acme.com` does not: a reader returning to your own docs is not a sale.

## Can different actions be worth different amounts?

Yes, with [goals](./mark-a-lead-or-sale.md). Give a goal a value — a demo request, a trial signup — and its value is completions × that value, counted once per visit. A goal without a value has no value; it is not treated as worth zero.

## What is "potential" on a reader?

A share of your average price, based on how closely that reader's visit resembles readers who converted before. It ranks readers by intent. It is not a forecast of money that will arrive, and adding it up does not give a pipeline.

## Can Genter use my real orders?

<!-- widget:callout type=warning -->

No. Genter does not import orders and does not send conversions to a CRM or billing system. For the real number, match the estimate against your own sales records.

<!-- /widget -->

## Related

<!-- widget:cards plain cols=2 -->

- [How do I mark what counts as a lead or a sale?](./mark-a-lead-or-sale.md) {target}
- [Why does Genter say "can't tell" instead of a number?](./cant-tell.md) {circle-question-mark}
- [Can leads from my pages go to HubSpot or another CRM?](../integrations/crm.md) {handshake}

<!-- /widget -->
