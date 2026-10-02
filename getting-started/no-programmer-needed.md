---
title: "Do I need a programmer to start with Genter?"
description: "No. Creating a project is a form: a name, your website, files or a short description is enough. Genter builds and hosts the site without code from you."
answers:
  - "Do I need a programmer to start with Genter?"  # buyer-questions.md #22
facts:
  - claim: "To start, one of these is enough: a project name, a website, a repository, files, or a product description."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard User Story 1; Genterai/app src/lib/create/newProject.ts (canContinue)"
  - claim: "Creating the project builds the site from a template, branding from your website and your files in one step, without calling an AI model."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard FR-001"
  - claim: "After creation, an agent drafts the pages from your website, or from your description when there is no website."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard FR-001; Genterai/app src/lib/automations/intent-catalog.ts (intent-docs-from-site, intent-docs-from-brief)"
  - claim: "A site hosted by Genter is live straight away, with nothing to connect."
    class: neutral
    source: "Genterai/app src/components/anon-draft/useDraftPublish.tsx (hosted option)"
  - claim: "The site address comes from the project name and is checked for availability before the project is created."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard FR-008, FR-009, FR-010; Genterai/app src/lib/create/projectName.ts"
---

# Do I need a programmer to start with Genter?

No. Creating a project in Genter is a form, not a setup: you write no code and install nothing.

## What do I need to start?

One of these is enough:

<!-- widget:cards plain cols=4 -->

- A project name {tag}
- Your website {globe}
- Files about your product {file-text}
- A short description of what you sell {message-square}

<!-- /widget -->

Genter then builds the site in one step: a template, your branding taken from your website, and your files. The site address comes from the project name and is checked for availability before the project is created.

## Who writes the pages?

An agent. After the project is created, it drafts the pages from your website — or from your description, when there is no website. A site hosted by Genter is live straight away, with nothing to connect.

## When is a technical person useful?

<!-- widget:callout type=tip -->

Only for steps you choose to take later, such as publishing to your own GitHub repository or pointing your own domain at the site. Starting does not need them.

<!-- /widget -->

## Related

<!-- widget:cards plain cols=2 -->

- [Can I use Genter without GitHub?](./without-github.md) {log-in}
- [How do I upload a document about what we sell if there's no website?](./upload-a-document.md) {file-up}

<!-- /widget -->
