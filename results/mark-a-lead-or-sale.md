---
title: "How do I mark what counts as a lead or a sale?"
description: "With goals: a goal counts one thing a reader does on your pages — opens a page, reaches a section, takes an action, or clicks out to your signup or checkout — and can carry a value. Goals chain into funnels."
answers:
  - "How do I mark what counts as a lead or a sale?"  # buyer-questions.md #51
facts:
  - claim: "A goal is one thing a reader does, of four kinds: opens a page, scrolls to a section, takes an action the pages already track, or clicks out to a site matched by host."
    class: neutral
    source: "Genterai/app src/lib/analytics/goals.ts (GoalKind); src/components/analytics/goals/GoalEditor.tsx (Page / Section / Action / Link out)"
  - claim: "A goal counts once per visit, however many times the reader does it in that visit."
    class: neutral
    source: "Genterai/specs specs/122-analytics-goals-funnels-readers FR-003"
  - claim: "A goal can carry a value per completion; without a value, money figures derived from it stay off instead of showing $0."
    class: neutral
    source: "Genterai/app src/lib/analytics/goal-validation.ts (zero_value)"
  - claim: "A goal on an action the pages never track is refused, because it could never fire."
    class: neutral
    source: "Genterai/app src/lib/analytics/goal-validation.ts (unknown_event)"
  - claim: "A new goal is matched against visits already recorded, not only future ones."
    class: neutral
    source: "Genterai/specs specs/122-analytics-goals-funnels-readers FR-001; Genterai/app src/lib/mcp/server-factory.ts (create_goal)"
  - claim: "Goals are created in the panel or by asking the agent in chat; both go through the same checks."
    class: neutral
    source: "Genterai/app src/lib/analytics/goal-write.ts; src/lib/agent/tools/analytics.ts (create_goal)"
  - claim: "A funnel is an ordered list of 2 to 8 goals; a reader reaches step N only after passing the earlier steps in order."
    class: neutral
    source: "Genterai/specs specs/122-analytics-goals-funnels-readers FR-004, FR-008"
  - claim: "Editing a goal keeps its history; deleting a goal archives it."
    class: neutral
    source: "Genterai/specs specs/122-analytics-goals-funnels-readers FR-007"
  - claim: "Goals count what readers do on the pages; they do not read payments or CRM records."
    class: neutral
    source: "Genterai/app src/lib/analytics/goals.ts (goals match reader events only)"
---

# How do I mark what counts as a lead or a sale?

With **goals**. A goal names one thing a reader does on your pages that matters to you — for example, clicking through to your signup or checkout. Genter counts it on every visit and, if you give it a value, turns the count into money.

## What can a goal be?

<!-- widget:cards plain cols=2 -->

- Page {file-check} {color:green}

  Counts when a reader opens a page. Example: the "Thank you" page after a request.

- Section {heading} {color:blue}

  Counts when a reader scrolls to a heading. Example: reaches "Pricing" on a long page.

- Action {mouse-pointer-click} {color:purple}

  Counts when a reader does something the pages already track. Example: copies code, searches, asks the assistant.

- Link out {external-link} {color:amber}

  Counts when a reader leaves for another site, matched by host. Example: clicks through to `app.example.com/signup`.

<!-- /widget -->

<!-- widget:callout type=note -->

A goal counts **once per visit**, however many times the reader does it in that visit. A goal on an action the pages never track is refused, because it could never fire.

<!-- /widget -->

## How do I give a goal a value?

Set a value per completion — for example, what a signup is worth to you. Without a value, money figures for that goal stay off rather than showing `$0`.

## How do I create one?

<!-- widget:tabs -->

### In the panel {layout-dashboard}

Open **Analytics** → **Goals** and press **New goal**.

### In chat {message-square}

Ask the agent, for example "count clicks to our signup page as a lead".

<!-- /widget -->

Both go through the same checks. A new goal is matched against visits already recorded, so numbers appear without waiting for new traffic.

## How do I follow a path, not one step?

Chain goals into a **funnel**: an ordered list of 2 to 8 goals. A reader reaches step 3 only after passing steps 1 and 2 in that order, so you see where readers drop off.

Editing a goal keeps its history; deleting it archives it.

## What goals do not see

<!-- widget:callout type=warning -->

Goals count what readers do **on your pages**. They do not read your payments or your CRM: the sale itself happens on your site, and a goal counts the step that leads to it.

<!-- /widget -->

## Related

<!-- widget:cards plain cols=2 -->

- [Can I see how many sales the pages brought?](./sales-from-pages.md) {circle-dollar-sign} {color:emerald}
- [Can leads from my pages go to HubSpot or another CRM?](../integrations/crm.md) {handshake} {color:orange}

<!-- /widget -->
