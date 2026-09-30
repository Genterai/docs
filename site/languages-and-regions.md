---
title: "In which languages and countries does Genter write pages and check answers?"
description: "Pages can be published in 15 languages. Search and AI answers are checked in one region per project, set as a two-letter country code; the default is the United States."
answers:
  - "In which languages and countries does Genter write pages and check answers?"  # buyer-questions.md #19
facts:
  - claim: "Pages can be published in 15 languages: English, Spanish, French, German, Portuguese, Italian, Russian, Chinese, Japanese, Korean, Arabic, Hindi, Turkish, Polish and Dutch."
    class: neutral
    source: "Genterai/app src/utils/constants.ts (SUPPORTED_LANGUAGES)"
  - claim: "The language your pages are written in is detected from your description, files or website."
    class: neutral
    source: "Genterai/specs specs/232-translation-language-surfaces-and-coverage FR-016; Genterai/app src/lib/create/docsLanguage.ts"
  - claim: "Translation runs in one of three modes: auto, manual or external."
    class: neutral
    source: "Genterai/specs specs/023-translations-runtime FR-019"
  - claim: "Until a page is translated, readers see the original page, and the menu stays in the original language with it."
    class: neutral
    source: "Genterai/specs specs/023-translations-runtime FR-003"
  - claim: "Switching a language off deletes nothing, and switching it back on does not translate unchanged pages again."
    class: neutral
    source: "Genterai/specs specs/232-translation-language-surfaces-and-coverage FR-019"
  - claim: "Right-to-left scripts are handled as one set shared by the site and the server."
    class: neutral
    source: "Genterai/specs specs/232-translation-language-surfaces-and-coverage FR-015"
  - claim: "Search and AI answers are checked in the project's region, set as any valid two-letter country code; the default is the United States."
    class: neutral
    source: "Genterai/specs specs/080-search-data-reads-and-pricing FR-003; Genterai/app src/lib/search-data/actor.ts (DEFAULT_SETTINGS, normalizeCountry)"
  - claim: "The region picker lists 26 countries: United States, United Kingdom, Canada, Australia, India, Germany, France, Spain, Italy, Netherlands, Sweden, Poland, Brazil, Mexico, Japan, South Korea, China, Singapore, Indonesia, Vietnam, Turkey, Ukraine, Russia, Israel, United Arab Emirates and South Africa."
    class: neutral
    source: "Genterai/app src/lib/search-data/actor.ts (REGIONS)"
  - claim: "The mention check reads results in the region set for the project."
    class: neutral
    source: "Genterai/specs specs/119-mentions-checks FR-012; Genterai/app src/lib/mentions/run.ts"
---

# In which languages and countries does Genter write pages and check answers?

Pages can be published in **15 languages**. Search results and AI answers are checked in **one region per project**, which you set as a country.

<!-- widget:stats cols=3 -->

- **15** — languages your pages can be published in {languages}
- **26** — countries in the region picker {globe}
- **1** — region per project at a time {map-pin}

<!-- /widget -->

## Which languages can my pages be in?

| | | |
|---|---|---|
| English | Spanish | French |
| German | Portuguese | Italian |
| Russian | Chinese | Japanese |
| Korean | Arabic | Hindi |
| Turkish | Polish | Dutch |

The language your pages are written in is detected from your description, files or website — you don't pick it by hand. Other languages are translations of those pages, in one of three modes: `auto`, `manual` or `external`. Right-to-left scripts such as Arabic are handled.

<!-- widget:cards plain cols=2 -->

- Until a page is translated {file-clock} {color:blue}

  Readers see the original page, and the menu stays in the original language with it — never a translated menu over an untranslated page.

- Switching a language off {toggle-left} {color:green}

  Deletes nothing. Switching it back on does not translate unchanged pages again.

<!-- /widget -->

## In which country are answers checked?

In your project's **region**, set as a two-letter country code. The default is the United States (`us`). The picker lists 26 countries:

United States, United Kingdom, Canada, Australia, India, Germany, France, Spain, Italy, Netherlands, Sweden, Poland, Brazil, Mexico, Japan, South Korea, China, Singapore, Indonesia, Vietnam, Turkey, Ukraine, Russia, Israel, United Arab Emirates, South Africa.

Any other valid two-letter country code is accepted too.

## Can one project be checked in several countries?

<!-- widget:callout type=note -->

A project is checked in one region at a time. Answers differ by country, so a reading for `de` says nothing about `us`.

<!-- /widget -->

## Related

<!-- widget:cards plain cols=2 -->

- [Which AI assistants does Genter check?](../visibility/which-ai-engines.md) {radar} {color:cyan}

<!-- /widget -->
