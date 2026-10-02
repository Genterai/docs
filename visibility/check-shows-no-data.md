---
title: "Why does the mention check show no data?"
description: "A mention check that shows nothing has a named reason: no saved questions, the check switched off, a $0 balance, an answer that came back empty, a refused list, or a read that failed."
answers:
  - "Why does the mention check show “no data”?"  # buyer-questions.md #52
facts:
  - claim: "With no saved questions the check records “No queries saved yet — nothing to check.”"
    class: neutral
    source: "Genterai/app src/lib/mentions/run.ts"
  - claim: "A new question reads “Not checked yet”; the first check runs within a few minutes, or on Check now."
    class: neutral
    source: "Genterai/app src/components/analytics/mentions/MentionsPanel.tsx"
  - claim: "A check with Check every day switched off records “Switched off — nothing checked.”"
    class: neutral
    source: "Genterai/app src/lib/mentions/run.ts; src/components/analytics/mentions/MentionsSettingsModal.tsx"
  - claim: "At a $0 balance the check does not start and records “Balance is $0 — nothing checked. Top up to resume mention checks.”"
    class: neutral
    source: "Genterai/app src/lib/mentions/run.ts; Genterai/specs specs/119-mentions-checks FR-012"
  - claim: "An empty answer is shown as “The last check came back empty”, never as “Not mentioned”."
    class: neutral
    source: "Genterai/specs specs/119-mentions-checks FR-010; Genterai/app MentionsPanel.tsx (verdictLine)"
  - claim: "A question list longer than the plan's quota is refused whole, with a message that names the limit."
    class: neutral
    source: "Genterai/specs specs/119-mentions-checks FR-002, FR-014"
  - claim: "When the search data read fails, the check records the error and its message instead of a result."
    class: neutral
    source: "Genterai/app src/lib/mentions/run.ts"
---

# Why does the mention check show no data?

A mention check shows nothing only when nothing was read, and it records why. Find your case below — the reason is also the last message on the check.

## No questions are saved

A check with an empty question list has nothing to ask. It records:

```text
No queries saved yet — nothing to check.
```

A new question reads **Not checked yet** until the first check runs — within a few minutes, or right away when you press **Check now**.

## The check is switched off

A switched-off check keeps its questions and earlier readings but asks nothing:

```text
Switched off — nothing checked.
```

Turn **Check every day** back on in the check's settings.

## The balance is $0

Each check reads live search data and is paid from your balance, so it does not start at $0:

```text
Balance is $0 — nothing checked. Top up to resume mention checks.
```

After a top-up the next scheduled check runs as usual, or press **Check now**.

## The answer came back empty

Sometimes an engine returns no answer or no results for a question. Genter then shows **The last check came back empty**, not **Not mentioned**: "not mentioned" is printed only when there was an answer to read. The next check asks again.

## The list was refused

A question list longer than your plan allows is refused whole, and the message names the limit and what to do. Nothing from a refused list is saved — trim it and save again.

## The read failed

When the search data read itself fails, the check records the error and its message instead of a result. Press **Check now** to try again.

## Related

<!-- widget:cards plain cols=2 -->

- [Which AI assistants does Genter check?](./which-ai-engines.md) {radar}
- [Why doesn't ChatGPT mention my product?](./why-ai-doesnt-name-you.md) {eye-off}

<!-- /widget -->
