---
title: "Can leads from my pages go to HubSpot or another CRM?"
description: "Not today: Genter sends nothing to HubSpot or any other CRM. What the HubSpot connection does instead, and how leads are counted inside Genter."
answers:
  - "Can I send leads from the pages to HubSpot or another CRM?"  # buyer-questions.md #56
facts:
  - claim: "No Genter connector sends data to HubSpot or another CRM; the HubSpot connection sends nothing."
    class: neutral
    source: "Genterai/app src/lib/integrations/registry.ts (HUBSPOT_APP sends: [], no Salesforce/Pipedrive connector)"
  - claim: "The HubSpot connection reads call notes and emails on recent deals, and contacts: who asked and from which kind of company."
    class: neutral
    source: "Genterai/app src/lib/integrations/registry.ts (hubspot_list_notes, hubspot_search_contacts)"
  - claim: "Goals count what a reader does on the pages, from visits already recorded, and can carry a value."
    class: neutral
    source: "Genterai/specs specs/122-analytics-goals-funnels-readers FR-001, FR-003"
---

# Can leads from my pages go to HubSpot or another CRM?

Not today. Genter sends nothing to HubSpot, Salesforce or any other CRM.

## What does the HubSpot connection do?

It works the other way round: Genter **reads** HubSpot and never writes to it.

- **Call notes and emails on recent deals** — the questions sales hears before a deal closes
- **Contacts** — who asked, and from which kind of company

The agent uses them to find the objections a page could answer once, instead of in every call.

## How are leads counted then?

Inside Genter, with goals. A goal counts one thing a reader does on your pages — for example, clicks through to your signup page — from visits already recorded, and can carry a value.

The signup form itself lives on your own site, and your CRM gets the lead from there, as it does today.

## Related

<!-- widget:cards plain cols=2 -->

- [Integrations](./README.md) {plug}

<!-- /widget -->
