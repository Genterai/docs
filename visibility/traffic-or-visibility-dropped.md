---
title: "What does Genter do if my traffic or search visibility drops?"
description: "Once a day Genter compares the last 7 full days with the 7 before. A drop in visits or in Google clicks or positions wakes the agent with the numbers, so it starts working on the drop instead of waiting for its next scheduled run."
answers:
  - "What does Genter do if traffic or visibility drops?"  # buyer-questions.md #58
facts:
  - claim: "A daily check compares the last 7 full days with the previous 7 days."
    class: neutral
    source: "Genterai/specs specs/253-genter-conductor-and-subagents FR-003; Genterai/app src/lib/genter/detectors.ts, src/app/api/cron/genter-watch/route.ts, vercel.json"
  - claim: "A traffic drop is visits down 25% or more, counted only when the earlier week had at least 200 visits; visits are unique visitors per day of the docs site, summed over the week."
    class: neutral
    source: "Genterai/app src/lib/genter/detectors.ts (TRAFFIC_DROP), src/lib/genter/watchData.ts (readVisits)"
  - claim: "A search visibility drop is Google clicks down 25% or more when the earlier week had at least 50 clicks, or the average position worse by 3 or more; it is read from Google Search Console data, with weeks ending on the last day Search Console has data for."
    class: neutral
    source: "Genterai/app src/lib/genter/detectors.ts (SEARCH_DROP), src/lib/genter/watchData.ts (readSearch)"
  - claim: "A drop wakes Genter at once; the run starts with the event name and a summary of the numbers."
    class: neutral
    source: "Genterai/app src/lib/webhook-dispatcher.ts, src/lib/genter/wake.ts (wakeLine)"
  - claim: "The same kind of drop wakes Genter at most once in 7 days per project."
    class: neutral
    source: "Genterai/app src/lib/genter/wakeEvents.ts (WAKE_COOLDOWN)"
  - claim: "Missing data is not read as a drop."
    class: neutral
    source: "Genterai/specs specs/253-genter-conductor-and-subagents FR-003; Genterai/app src/lib/genter/detectors.ts"
  - claim: "Only projects where Genter is switched on are checked; when Genter is off, a drop wakes nothing."
    class: neutral
    source: "Genterai/app src/lib/genter/watchData.ts (listWatchedProjects), src/lib/genter/wake.ts"
  - claim: "A woken run passes the same gates as any Genter run: the plan, the daily limit and the wallet."
    class: neutral
    source: "Genterai/specs specs/253-genter-conductor-and-subagents FR-001; Genterai/app src/lib/genter/wake.ts (fireAutomation)"
  - claim: "The agent's playbooks for a drop include explaining a traffic drop, breaking traffic down by source, comparing the pages that lost the most, explaining a drop in Google and checking indexing."
    class: neutral
    source: "Genterai/skill skills/genter-intents/assets/intents.json (traffic-drop, traffic-sources, page-loss-compare, search-drop, index-check)"
  - claim: "The set of events that wake Genter is fixed in the product and is not configured by the owner; mentions in AI answers are not part of the daily drop check."
    class: neutral
    source: "Genterai/specs specs/253-genter-conductor-and-subagents FR-002; Genterai/app src/lib/genter/wakeEvents.ts (GENTER_WAKE_EVENTS)"
---

# What does Genter do if my traffic or search visibility drops?

Genter notices the drop itself and wakes up to work on it. Once a day it compares the last 7 full days with the 7 days before. When visits or Google results fall past a set threshold, the agent starts a run at once, with the numbers, instead of waiting for its next scheduled run.

## What counts as a drop?

| What fell | Counted as a drop when | Read from |
|---|---|---|
| Traffic | visits are down **25% or more**, and the earlier week had at least **200** visits | visits to your docs site — unique visitors per day, summed over the week |
| Search visibility | Google clicks are down **25% or more** (earlier week at least **50** clicks), **or** the average position is worse by **3 or more** | Google Search Console |

Search Console reports with a delay of a few days, so the two weeks for search end on the last day it has data for.

Small sites are not judged on noise: below the minimum volume the check does not call a drop at all.

## What happens when a drop is found?

1. Genter is woken right away. The run starts with what woke it — `traffic_drop` or `search_visibility_drop` — and a summary of the numbers.
2. The agent decides what to look into. Its playbooks for a drop include explaining a traffic drop, breaking traffic down by source, comparing the pages that lost the most, explaining a drop in Google and checking indexing.
3. Changes to your pages go the usual way — as a pull request, under your review mode. See [Does Genter publish on its own?](../publishing/does-genter-publish-on-its-own.md)

The same kind of drop wakes Genter at most **once in 7 days** per project, so a long slide does not start a new run every day.

## When does a drop wake nothing?

- **Genter is switched off** for the project. Only projects where Genter is on are checked.
- **There is no data.** A missing source — no visits recorded, Search Console not connected — is not read as a drop.
- **The run cannot start.** A woken run passes the same gates as any Genter run: your plan, the daily limit and the wallet.

## Does it watch mentions in AI answers too?

Not with this daily check. It covers site visits and Google search only. Whether AI assistants name your product is measured separately — see [Which AI assistants does Genter check?](./which-ai-engines.md)

The list of events that wake Genter is fixed in the product; you do not set it up.

## Related

<!-- widget:cards plain cols=2 -->

- [AI and search visibility](./README.md) {radar} {color:gray}
- [Why does the mention check show no data?](./check-shows-no-data.md) {circle-dashed} {color:gray}

<!-- /widget -->
