---
title: "Customers say they found us through ChatGPT — how do I check?"
description: "Genter counts visits that arrive from ChatGPT, Perplexity, Claude, Copilot and Gemini as their own channel, “AI assistant”. The count is a floor: a visit whose referrer was stripped shows as Direct."
answers:
  - "Customers say they found us through ChatGPT — how can I check that?"  # buyer-questions.md #10
facts:
  - claim: "A visit whose referrer is chatgpt.com, chat.openai.com, perplexity.ai, claude.ai, copilot.microsoft.com or gemini.google.com is counted in the “AI assistant” channel."
    class: neutral
    source: "Genterai/app src/utils/analytics/traffic-source.ts (AI_REFERRER_HOSTS, classifyTrafficSource); src/components/analytics/BreakdownCard.tsx (channel labels)"
  - claim: "A visit with no referrer, or whose referrer the browser or app stripped, is counted as Direct."
    class: neutral
    source: "Genterai/app src/utils/analytics/traffic-source.ts (classifyTrafficSource)"
  - claim: "When an AI assistant fetches a page on behalf of a user (for example ChatGPT-User or Perplexity-User), Genter records the fetch separately from ordinary crawlers."
    class: neutral
    source: "Genterai/app src/utils/analytics/traffic-source.ts (AI_REFERRAL_UAS); src/lib/ai-activity.ts"
  - claim: "Traffic sources are read from the self-reported referrer and user agent."
    class: neutral
    source: "Genterai/app src/utils/analytics/traffic-source.ts (header: user-agents are self-reported and unverified)"
  - claim: "Bots and the owner's and team's own visits are left out of reader counts."
    class: neutral
    source: "Genterai/specs specs/121-analytics-visits-headline FR-004, FR-005"
  - claim: "Genter does not link a single customer, lead or deal to the assistant that sent them."
    class: neutral
    source: "Genterai/app src/lib/integrations/registry.ts (no connector sends visits to a CRM); src/utils/analytics/traffic-source.ts (classification per visit only)"
---

# Customers say they found us through ChatGPT — how do I check?

Look at the **AI assistant** channel. Genter counts visits that arrive from an AI assistant's answer as their own channel, next to organic search, direct and the others.

## Which assistants are counted?

A visit is counted as **AI assistant** when it arrives from one of these sites:

<!-- widget:cards bare cols=3 -->

- ChatGPT {logos:openai-icon}

  `chatgpt.com`, `chat.openai.com`

- Perplexity {logos:perplexity-icon}

  `perplexity.ai`

- Claude {logos:claude-icon}

  `claude.ai`

- Copilot {sparkles}

  `copilot.microsoft.com`

- Gemini {logos:google-gemini-icon}

  `gemini.google.com`

<!-- /widget -->

Bots and your own team's visits are left out, so the count is readers.

## Why can the number be lower than what customers tell me?

<!-- widget:callout type=warning -->

It is a **floor**. Genter can only see an assistant when the visit carries it as the referrer. When a browser or an app strips the referrer — or the customer types your address after reading the answer — the visit is counted as **Direct**.

<!-- /widget -->

Sources are read from what the browser reports. A spoofed referrer is taken at face value.

## Does ChatGPT read my pages when it answers?

Genter records that too, separately. When an assistant fetches one of your pages on behalf of a user — for example `ChatGPT-User` or `Perplexity-User` — the fetch is recorded apart from ordinary crawlers. It is the assistant reading, not a customer visiting, and it is not counted as a reader.

## Can I see which customer came from ChatGPT?

No. Genter counts visits by channel; it does not tie a single customer, lead or deal to the assistant that sent them. To connect a sale to its source, ask the customer where they found you, as you do today.

## Related

<!-- widget:cards plain cols=2 -->

- [How many visitors am I losing because people ask AI instead of Google?](./visitors-lost-to-ai.md) {trending-down}
- [Which AI assistants does Genter check?](./which-ai-engines.md) {radar}

<!-- /widget -->
