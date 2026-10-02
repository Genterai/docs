---
title: "Does Genter publish on its own, or does everything wait for my approval?"
description: "Every change Genter makes to your pages is a pull request. The project's review mode decides whether it merges at once (auto) or waits for you (manual); a blocking question holds it either way."
answers:
  - "Does Genter publish on its own, or does everything go to me for approval?"  # buyer-questions.md #20
facts:
  - claim: "Every change to the pages opens a pull request; the review mode decides only whether it is merged in the same step."
    class: neutral
    source: "Genterai/specs specs/234-doc-lifecycle-review-policy-and-content-review FR-005; Genterai/app src/lib/review/policy.ts"
  - claim: "In auto mode the pull request is merged at once and the change is live; in manual mode nothing is published until the owner approves it in the Pull Requests section of the panel or on GitHub."
    class: neutral
    source: "Genterai/app src/lib/review/policy.ts"
  - claim: "An open question marked as blocking holds the merge even in auto mode, until the owner answers."
    class: neutral
    source: "Genterai/specs specs/234-doc-lifecycle-review-policy-and-content-review FR-006; Genterai/app src/lib/review/policy.ts"
  - claim: "The default review mode is auto; any value other than manual is read as auto."
    class: neutral
    source: "Genterai/specs decisions/0004 (point 5); Genterai/app src/lib/review/policy.ts"
---

# Does Genter publish on its own, or does everything wait for my approval?

Both are possible, and you choose. Every change Genter makes to your pages opens a **pull request**. The project's **review mode** decides only one thing: whether that pull request is merged in the same step.

| Review mode | What happens |
|---|---|
| `auto` (default) | The pull request is opened and merged at once — the change is live |
| `manual` | The pull request is opened and waits — nothing is published until you approve it |

In `manual` mode you approve or reject the change in the **Pull Requests** section of the panel, or on GitHub.

## What if Genter is not sure?

When the agent needs an answer only you can give, it asks you instead of guessing. A question marked as **blocking** holds the merge even in `auto` mode: the pull request stays open until you answer, and nothing is published before that.

## Can I see what was changed?

Yes. Every change is a pull request in your repository, merged or not. The diff and the reasons behind it stay readable there after the change is live.

## Related

<!-- widget:cards plain cols=2 -->

- [Publishing](./README.md) {plug}

<!-- /widget -->
