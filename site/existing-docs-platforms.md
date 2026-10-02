---
title: "Does Genter work with docs already on Mintlify, GitBook or Docusaurus?"
description: "Genter reads your published docs on Mintlify, GitBook, Docusaurus and other platforms as a source. It does not write back to those platforms: the pages it writes live on your Genter site."
answers:
  - "Does Genter work with documentation that's already on Mintlify, GitBook or Docusaurus?"  # buyer-questions.md #17
facts:
  - claim: "A published docs site can be connected as a source by its address; the agent reads its pages as material."
    class: neutral
    source: "Genterai/specs specs/102-documentation-sources (Overview, FR-002)"
  - claim: "Recognised docs platforms include Mintlify, GitBook, ReadMe, Docusaurus, Read the Docs, MkDocs, Nextra, Fumadocs, VitePress, Starlight, Docsify, Archbee, Document360, Redocly, Stoplight, Scalar and Bump.sh."
    class: neutral
    source: "Genterai/app src/lib/sources/catalog.ts (category docs-platform)"
  - claim: "A site source is read from its sitemap first; without a sitemap only the entry page is read, and the result says so."
    class: neutral
    source: "Genterai/specs specs/102-documentation-sources FR-007"
  - claim: "Before writing, the agent is told the gap between the number of documentation pages in the source and on your site."
    class: neutral
    source: "Genterai/specs specs/102-documentation-sources FR-009"
  - claim: "No Genter connector writes to Mintlify, GitBook, Docusaurus or the other docs platforms."
    class: neutral
    source: "Genterai/app src/lib/sources/catalog.ts (all docs-platform entries connect by url, read only)"
---

# Does Genter work with docs already on Mintlify, GitBook or Docusaurus?

Genter **reads** them. It does not write back to them: the pages Genter writes live on your Genter site.

## What does Genter do with my existing docs?

Connect your published docs as a source by pasting their address. The agent reads the pages as material, so it carries over what your docs already say instead of guessing.

Recognised platforms:

<!-- widget:cards bare cols=3 -->

- Mintlify {simple-icons:mintlify}
- GitBook {simple-icons:gitbook}
- ReadMe {simple-icons:readme}
- Docusaurus {logos:docusaurus}
- Read the Docs {simple-icons:readthedocs}
- MkDocs {book-open}
- Nextra {simple-icons:nextra}
- Fumadocs {book-open}
- VitePress {simple-icons:vitepress}
- Starlight {book-open}
- Docsify {simple-icons:docsify}
- Archbee {book-open}
- Document360 {book-open}
- Redocly {book-open}
- Stoplight {logos:stoplight}
- Scalar {simple-icons:scalar}
- Bump.sh {book-open}

<!-- /widget -->

## How much of my site does it read?

It starts from the site's sitemap.

<!-- widget:callout type=note -->

Without a sitemap, only the entry page is read — and the result says so, so a short read is not mistaken for a short site.

<!-- /widget -->

Before writing, the agent is told how many documentation pages your source has and how many your Genter site has, so the gap is visible.

## Can Genter edit my pages on Mintlify or GitBook?

<!-- widget:callout type=warning -->

No. No Genter connector writes to these platforms.

<!-- /widget -->

## Related

<!-- widget:cards plain cols=2 -->

- [Can I use Genter without GitHub?](../getting-started/without-github.md) {log-in}

<!-- /widget -->
