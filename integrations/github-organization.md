---
title: "How do I connect a whole GitHub organization?"
description: "Install Genter's GitHub App on the organization from the GitHub card in Integrations, and choose all repositories or selected ones on GitHub's own screen. An organization member without install rights sends the request to an owner."
answers:
  - "How do I connect a whole GitHub organization?"  # buyer-questions.md #47
facts:
  - claim: "A GitHub account is connected by installing the GitHub App on the chosen user or organization; no token is stored for it."
    class: neutral
    source: "Genterai/specs specs/099-integrations-catalog-and-accounts FR-016; Genterai/app src/app/api/integrations/github/install/route.ts"
  - claim: "Which repositories the connection covers is what you grant on GitHub's install screen: all repositories or selected ones."
    class: neutral
    source: "Genterai/app src/app/api/integrations/github/install/route.ts (repository_selection); Genterai/specs specs/097-github-credentials-and-read-authority FR-003"
  - claim: "Several GitHub accounts and organizations can be connected."
    class: neutral
    source: "Genterai/app src/lib/integrations/registry.ts (GITHUB_APP multiAccount)"
  - claim: "An organization member who cannot install apps sends a request to an organization owner; the connection appears once an owner approves it."
    class: neutral
    source: "Genterai/specs specs/099-integrations-catalog-and-accounts FR-016; Genterai/app src/app/api/integrations/github/install/route.ts (setup_action request)"
  - claim: "If GitHub does not bring you back after the install, connecting again finds the installation that belongs to your sign-in."
    class: neutral
    source: "Genterai/specs specs/097-github-credentials-and-read-authority FR-017; Genterai/app src/lib/integrations/githubInstallations.ts"
  - claim: "With the connection, the agent can read files, list commits, releases and pull requests, and open an issue in the repositories you granted."
    class: neutral
    source: "Genterai/app src/lib/integrations/registry.ts (GITHUB_APP tools)"
  - claim: "A private repository is read only when the App's installation includes it."
    class: neutral
    source: "Genterai/specs specs/097-github-credentials-and-read-authority FR-003"
  - claim: "The project wizard accepts a github.com/owner/repo address as a repository; an organization page address is not a repository."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard FR-007"
  - claim: "Projects created while an organization is open in Genter belong to that organization."
    class: neutral
    source: "Genterai/specs specs/173-project-creation-wizard FR-029"
---

# How do I connect a whole GitHub organization?

Install Genter's **GitHub App** on the organization. You choose which repositories it covers on GitHub's own install screen — all of them, or a selection.

## Steps

1. In the panel, open **Integrations** and choose **GitHub**.
2. Connect. GitHub opens its install screen.
3. Pick the **organization**.
4. Choose **All repositories**, or **Only select repositories** and tick the ones Genter should see.
5. Install. GitHub brings you back to the panel with the organization connected.

If GitHub does not bring you back, connect again: Genter finds the installation that belongs to your sign-in.

No token is stored for the connection: it is the App installation itself.

## I'm a member, not an owner, of the organization

If you cannot install apps on the organization, GitHub sends your request to an organization owner. The connection appears once an owner approves it.

## What can the agent do with it?

In the repositories you granted, it can read files, list commits, releases and pull requests, and open an issue. A private repository is read only when the installation includes it — with **Only select repositories**, add it to the list on GitHub.

You can connect several GitHub accounts and organizations.

## How do I turn repositories into projects?

Create a project and paste a repository address, `github.com/<owner>/<repo>`. An organization page address is not a repository, so each repository is added as its own project.

To keep your team's projects together, open your organization in Genter first: projects created while it is open belong to it.

## Related

- [Can I use Genter without GitHub?](../getting-started/without-github.md)
- [Integrations](./README.md)
