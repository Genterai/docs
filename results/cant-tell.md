---
title: "Why does Genter say “can't tell” instead of a number?"
description: "Because the number would be noise. Genter shows no percentage below 30 visits, judges a change only when both periods have enough visits and the after-period is over, and leaves a missing figure empty instead of printing 0."
answers:
  - "Why does Genter write “can't tell yet” instead of a number?"  # buyer-questions.md #35
facts:
  - claim: "Below 30 visits, percentage rates are not shown; only counts are."
    class: neutral
    source: "Genterai/app src/utils/analytics/sessions.ts (MIN_SESSIONS_FOR_RATE = 30); Genterai/specs specs/043-mcp-measurement-loop-tools SC-003"
  - claim: "To judge whether a change worked, Genter needs at least 30 visits both before and after; otherwise the verdict is “Can't tell” for a low sample."
    class: neutral
    source: "Genterai/app src/lib/change-history/forecast-verdict.ts (low_sample); src/components/chain/ChainBadge.tsx (Can't tell)"
  - claim: "While the after-period has not finished, the verdict is “Can't tell”, because a partial period is not comparable to a full one."
    class: neutral
    source: "Genterai/app src/lib/change-history/forecast-verdict.ts (partial_after_window)"
  - claim: "When a metric was zero before the change, no percentage change is computed; only the raw movement is shown."
    class: neutral
    source: "Genterai/app src/lib/change-history/forecast-verdict.ts (no_baseline); Genterai/specs specs/121-analytics-visits-headline FR-009"
  - claim: "Edited pages are credited only when they moved better than a control group of untouched pages; without a control the answer is an explicit “cannot tell”."
    class: neutral
    source: "Genterai/app src/lib/mcp/page-diff-impact.ts (judge); Genterai/specs specs/043-mcp-measurement-loop-tools SC-002"
  - claim: "A figure that cannot be said is shown empty, never as 0."
    class: neutral
    source: "Genterai/app src/utils/analytics/headline.ts; Genterai/specs specs/121-analytics-visits-headline FR-008"
---

# Why does Genter say "can't tell" instead of a number?

Because the number it could print would be noise, and a noisy number reads like a measurement. When the data cannot support a figure, Genter says **Can't tell** and names why.

## Too few visits

- **Below 30 visits,** Genter shows counts, not percentages. "2 of 3 readers left" is a fact; "67% bounce" from three visits is noise.
- **To judge a change,** it needs at least 30 visits both before and after it. With fewer, the verdict is **Can't tell** for a low sample.

## The period is not over

A change is judged on a full period after it. Until that period has finished, the verdict is **Can't tell**: half a week is not comparable to a whole one.

## Nothing to compare against

- **A zero before.** If a figure was `0` before the change, there is no percentage to compute — growth from zero is not "+100%". Genter shows the raw movement instead.
- **No control.** Traffic moves for reasons that have nothing to do with your pages — a season, a launch, a search update. So edited pages are credited only when they moved **better than** a group of pages that were not touched. Without such a control, the answer is "can't tell", not a guess.

## Empty is not zero

A figure Genter cannot state is left empty (`—`), never shown as `0`. Zero would read as "we measured and nothing happened"; empty means "not measured".

## Related

- [Can I see how many sales the pages brought?](./sales-from-pages.md)
- [How does Genter keep pages current when the product changes?](../publishing/keeping-pages-current.md)
