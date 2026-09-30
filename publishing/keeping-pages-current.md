---
title: "How does Genter keep pages current when the product changes?"
description: "Every page carries a status and a version, every change is a pull request, a change history measures each commit, and connected sources give the agent the current facts. A page is never refreshed by age alone."
answers:
  - "How does Genter keep pages current when the product changes?"  # buyer-questions.md #60
facts:
  - claim: "Each page keeps a status — Generated, Draft, In review, Approved, Locked, Deprecated or Archived — and a version in its own frontmatter."
    class: neutral
    source: "Genterai/app src/lib/doc-lifecycle/statuses.json; Genterai/specs specs/234-doc-lifecycle-review-policy-and-content-review FR-001"
  - claim: "A page written by the agent starts as Generated; agents do not build new work on Generated, Draft or In review pages, only on Approved or Locked ones."
    class: neutral
    source: "Genterai/app src/lib/doc-lifecycle/statuses.json (agentMayBuildFrom)"
  - claim: "Editing an approved page raises its version and returns it to In review."
    class: neutral
    source: "Genterai/app src/lib/doc-lifecycle/statuses.json (approved); Genterai/specs specs/234-doc-lifecycle-review-policy-and-content-review User Story 1"
  - claim: "Agents cannot rewrite a Locked page."
    class: neutral
    source: "Genterai/app src/lib/doc-lifecycle/statuses.json (agentMayOverwrite: false)"
  - claim: "Every change to the pages opens a pull request; the review mode decides whether it merges at once or waits for the owner."
    class: neutral
    source: "Genterai/app src/lib/review/policy.ts; Genterai/specs specs/234-doc-lifecycle-review-policy-and-content-review FR-005"
  - claim: "The change history lists each documentation commit and compares the 7 days before it with the 7 days after, once 14 days have passed."
    class: neutral
    source: "Genterai/specs specs/176-change-history FR-001"
  - claim: "Only a before/after comparison against a control group is called a result; other evidence is labelled as a direction or as a prediction from the diff."
    class: neutral
    source: "Genterai/specs specs/176-change-history FR-011"
  - claim: "A repository, website or page can be connected as a source the agent reads when it writes or updates pages."
    class: neutral
    source: "Genterai/specs specs/102-documentation-sources (Overview, FR-006, FR-007)"
---

# How does Genter keep pages current when the product changes?

By tracking the state of every page, reading your product's current sources before it writes, and putting every update through a pull request you can review.

## Where do current facts come from?

From **sources** you connect: your repository, your website, or a single page. The agent reads them as material when it writes or updates a page, so a new fact enters the page from the place where your product is described, not from memory.

## How do I know which pages are trusted?

Every page carries a **status** and a **version** in its own frontmatter, so both travel with the page:

| Status | What it means |
|---|---|
| Generated | Written by the agent, not yet read by a person |
| Draft | Being written |
| In review | Waiting for a person to approve it |
| Approved | Signed off |
| Locked | Signed off; agents cannot rewrite it |
| Deprecated | Still published, no longer current |
| Archived | Out of use |

Agents build new work only on **Approved** or **Locked** pages. Editing an approved page raises its version and returns it to **In review**: the sign-off was for the old text.

## How does an update reach the site?

As a pull request. The project's review mode decides whether it merges at once or waits for you — see [Does Genter publish on its own?](./does-genter-publish-on-its-own.md)

## Did the update help?

The **change history** lists each documentation commit and compares traffic in the 7 days before it with the 7 days after, once 14 days have passed. Only a comparison against a control group is called a result; weaker evidence is labelled as a direction, or as a prediction from the change itself.

## Related

- [Does Genter publish on its own, or does everything wait for my approval?](./does-genter-publish-on-its-own.md)
- [Does Genter work with docs already on Mintlify, GitBook or Docusaurus?](../site/existing-docs-platforms.md)
