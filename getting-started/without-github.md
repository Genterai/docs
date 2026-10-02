---
title: "Can I use Genter without GitHub?"
description: "Yes. You can sign in with an email code, create a project from a name, your website, files or a description, and let Genter host the site. GitHub is optional."
answers:
  - "Can I use Genter without GitHub?"  # buyer-questions.md #15
facts:
  - claim: "You can sign in with a one-time code sent to your email, without a GitHub account."
    class: neutral
    source: "Genterai/app src/auth.ts (Credentials provider email-otp)"
  - claim: "A project can be started from any one of: a name, a website, a repository, files, or a product description."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard User Story 1; Genterai/app src/lib/create/newProject.ts (canContinue)"
  - claim: "When Genter hosts the site, there is nothing to connect and the site is live straight away."
    class: neutral
    source: "Genterai/app src/components/anon-draft/useDraftPublish.tsx (hosted option)"
  - claim: "You can instead publish to a new repository in your own GitHub account; that needs write access to GitHub."
    class: neutral
    source: "Genterai/app src/components/anon-draft/useDraftPublish.tsx (My own GitHub option)"
  - claim: "The site address is set in the panel and does not read GitHub."
    class: neutral
    source: "Genterai/app src/components/admin-cards/cards/SiteAddressCard.tsx"
  - claim: "Importing your own repository writes nothing into it at creation."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard FR-003"
---

# Can I use Genter without GitHub?

Yes. You can sign in, create a project and have a live site without a GitHub account.

## How do I start without GitHub?

<!-- widget:stepper -->

### Sign in with your email

Genter sends a one-time code; no GitHub login is needed.

### Give Genter something about your product

Any one of these is enough: a name, your website, files, or a short description.

### Let Genter host the site

There is nothing to connect, and the site is live straight away.

<!-- /widget -->

The site address is set in the panel, and it does not depend on GitHub either.

## When would I connect GitHub?

Only if you want the pages in a repository you own:

| Option | What it needs |
|---|---|
| Genter hosts the site | Nothing to connect |
| A new repository in your own GitHub account | Write access to your GitHub |
| An existing repository of yours | Importing it; Genter writes nothing into it when the project is created |

## Related

<!-- widget:cards plain cols=2 -->

- [Do I need a programmer to start with Genter?](./no-programmer-needed.md) {rocket}
- [How do I upload a document about what we sell if there's no website?](./upload-a-document.md) {file-up}

<!-- /widget -->
