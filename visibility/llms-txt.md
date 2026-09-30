---
title: "Why Genter, if I can just add llms.txt to my site?"
description: "Genter builds llms.txt and llms-full.txt for your site on its own. The file is one part of the work: Genter also checks whether AI assistants name you and checks each change against what it was expected to do."
answers:
  - "Why use Genter if I can just add llms.txt to my site?"  # buyer-questions.md #24
facts:
  - claim: "Genter builds llms.txt (a short index in the llmstxt.org format) and llms-full.txt (the full text of every page) for your site."
    class: neutral
    source: "Genterai/specs specs/181-llms-txt (Overview); Genterai/app src/app/[user]/llms.txt/route.ts, src/app/[user]/llms-full.txt/route.ts"
  - claim: "Each page in llms.txt is listed by its title with two addresses: the page and its Markdown version."
    class: neutral
    source: "Genterai/specs specs/181-llms-txt FR-001, FR-002a"
  - claim: "llms.txt names the site's languages and gives an example of a translated address."
    class: neutral
    source: "Genterai/specs specs/181-llms-txt FR-003"
  - claim: "Private sites and projects that opted out of AI visibility are left out of these files."
    class: neutral
    source: "Genterai/specs specs/181-llms-txt FR-005, FR-006; Genterai/app src/lib/generate-workspace-llms-txt.ts"
  - claim: "A very large site's llms-full.txt is capped, and the file says so at the top."
    class: neutral
    source: "Genterai/specs specs/181-llms-txt FR-008"
  - claim: "The mention check asks saved buyer questions and records whether an AI answer names you, and where you stand in search results and who else is there."
    class: neutral
    source: "Genterai/specs specs/119-mentions-checks FR-001, FR-011"
  - claim: "A change can state what it should do — which page, which measurement, the target and the date to check; on that date Genter compares the readings before and after."
    class: neutral
    source: "Genterai/specs specs/112-pr-expectations-impact FR-008, FR-013"
  - claim: "The verdict is computed from two recorded readings, not by a model, and is one of four outcomes: worked, made worse, no distinguishable effect, or can't tell."
    class: neutral
    source: "Genterai/specs specs/112-pr-expectations-impact (Overview), FR-015; Genterai/app src/lib/change-history/forecast-verdict.ts"
---

# Why Genter, if I can just add llms.txt to my site?

`llms.txt` is one file. Genter builds it for your site on its own — and treats it as one part of the work, next to two things a file cannot do: checking whether AI assistants actually name you, and checking whether each change did what it was meant to.

## What does Genter put in llms.txt?

Genter builds two files and keeps them in step with your pages:

- **`llms.txt`** — a short index in the [llmstxt.org](https://llmstxt.org) format. Each page is listed by its title with two addresses: the page and its Markdown version. The file also names the site's languages and shows how a translated address looks.
- **`llms-full.txt`** — the full text of every page. On a very large site it is capped, and the file says so at the top.

A private site, or a project that opted out of AI visibility, is left out of both.

## What does a file alone not tell me?

Whether it changed anything. `llms.txt` hands AI assistants a list of your pages; it does not tell you what they answer. Genter adds two checks around it:

| Check | What it records |
|---|---|
| **Mention check** | Your buyers' saved questions, asked to AI assistants and search engines: whether the answer names you, where you rank, and who else is there |
| **Expectation on a change** | What a change should do — which page, which measurement, the target and the date to check. On that date Genter compares the readings before and after |

The verdict on a change is computed from the two recorded readings, not by a model, and is one of four: **worked**, **made worse**, **no distinguishable effect**, or **can't tell**.

## Related

- [Which AI assistants does Genter check?](./which-ai-engines.md)
- [Why doesn't ChatGPT mention my product?](./why-ai-doesnt-name-you.md)
- [What are GEO and AEO, and how are they different from SEO?](./geo-vs-seo.md)
