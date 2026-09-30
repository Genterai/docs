---
title: "How do I upload a document about what we sell if there's no website?"
description: "Attach it when you create the project: PDF, DOCX, Markdown or plain text, up to 15 MB each. Without a website, the agent writes the pages from your description and files."
answers:
  - "How do I upload a document about what we sell if we don't have a website?"  # buyer-questions.md #48
facts:
  - claim: "Files can be PDF, DOCX, Markdown (.md, .markdown, .mdx) or plain text."
    class: neutral
    source: "Genterai/app src/lib/files/page.ts (UPLOAD_EXTENSIONS, isSupportedUpload)"
  - claim: "Each file can be up to 15 MB; text beyond about 120,000 characters is cut, and the cut is marked."
    class: neutral
    source: "Genterai/app src/lib/files/page.ts (MAX_UPLOAD_BYTES, MAX_EXTRACTED_CHARS)"
  - claim: "Any one of a name, a website, a repository, files or a description is enough to create a project."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard User Story 1"
  - claim: "Files are turned into text without an AI model when the project is created."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard FR-001; Genterai/app src/lib/files/page.ts"
  - claim: "The description is a brief for the agent and is never shown as a page."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard FR-005"
  - claim: "Without a website, the agent writes from the brief: it does not look for a site, keeps the template to what the description and files support, and lists the gaps as questions in its report."
    class: neutral
    source: "Genterai/app src/lib/automations/docs-from-site.ts (pickDocsIntent); src/lib/automations/intent-catalog.ts (intent-docs-from-brief)"
  - claim: "Attached files are handed to the agent as material for the run; when the run cannot start, the files are published as pages instead."
    class: neutral
    source: "Genterai/app src/lib/automations/handoff.ts; src/lib/automations/docs-from-site.ts"
  - claim: "Images are stored as assets that pages can show; the agent does not see their pixels."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard FR-021; Genterai/app src/lib/automations/handoff.ts"
  - claim: "A file with no readable text is named as unreadable instead of being skipped silently."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard FR-020"
---

# How do I upload a document about what we sell if there's no website?

Attach it when you create the project. A website is not needed: a document, or a short description, is enough to start.

## Which files can I attach?

<!-- widget:cards plain cols=4 -->

- PDF {file-text} {color:red}

  `.pdf`

- DOCX {file-type} {color:blue}

  `.docx`

- Markdown {file-code} {color:purple}

  `.md`, `.markdown`, `.mdx`

- Plain text {file} {color:gray}

  `.txt`

<!-- /widget -->

Each file can be up to **15 MB**.

Files are turned into text when the project is created, without an AI model. Text beyond about 120,000 characters is cut, and the cut is marked. A file with no readable text — a scanned image in a PDF, for example — is named as unreadable, not skipped silently.

Images you add are kept so pages can show them. The agent reads text; it does not see what is in a picture.

## What happens to the document?

It becomes **material for the agent**. With no website to read, the agent writes your pages from your description and files: it does not go looking for a site, it keeps the pages to what your material supports, and it lists what it could not confirm as questions in its report.

If the run cannot start, your files are not lost: they are published as pages instead.

<!-- widget:callout type=warning -->

Pages are as public as your site is — keep a confidential document out of a public project.

<!-- /widget -->

The description you type is a brief for the agent. It is never shown as a page.

## Related

<!-- widget:cards plain cols=2 -->

- [Can I use Genter without GitHub?](./without-github.md) {log-in} {color:blue}
- [How much of my time does Genter take, and what will it ask me?](./your-time-and-questions.md) {clock} {color:amber}

<!-- /widget -->
