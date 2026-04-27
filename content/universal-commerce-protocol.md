---
title: "Universal Commerce Protocol (UCP)"
type: concept
topic: agentic-money
tags: [infrastructure, agentic-commerce, identity-kyc]
sources: ["2957-4390-068.2026.issue-004-en.pdf"]
created: 2026-04-26
updated: 2026-04-26
---

# Universal Commerce Protocol (UCP)

**One-line:** Google's protocol (January 2026) that standardizes how businesses connect with AI agents across the full shopping journey — discovery, comparison, offer, and checkout — enabling purchases directly within AI interfaces like Google Search AI Mode and Gemini.

## How it works

UCP provides a "shared grammar" for:
1. **Discovery** — agents find relevant products across merchants
2. **Comparison** — agents evaluate options against user preferences
3. **Offer** — merchants present personalized offers to agent-mediated buyers
4. **Checkout** — "Native Checkout" allows users to buy without leaving the AI surface

Example: a user in Google Gemini says "buy me a blue wool sweater under $80 with free shipping" → Gemini uses UCP to query merchants (Etsy, Wayfair, etc.), compares options, and completes checkout without the user opening a browser tab.

## Relationship to AP2

UCP handles the commerce workflow (discovery → offer) at Layer 1 (Intent and Orchestration) of the IMF's three-layer model. AP2 handles Layer 2 (authorization and control). Together they form a complete pipeline: UCP finds and structures intent, AP2 authenticates and authorizes execution.

The IMF Note identifies UCP as one of the most impactful standards for Layer 1, alongside MCP and A2A.

## Live implementations

- **Google Search AI Mode** — Native Checkout for qualifying merchants
- **Google Gemini** — Shopping via UCP (Etsy, Wayfair confirmed)

## Significance

UCP positions Google as the commerce discovery layer for the agentic web, parallel to how Google Search dominated web discovery for humans. If UCP becomes the standard for agent-to-merchant communication, Google controls the top of the agentic commerce funnel.

## Primary source

Published January 2026. Spec available at [developers.google.com/merchant/ucp](https://developers.google.com/merchant/ucp).

## Related concepts

- [[ap2]]
- [[agentic-commerce]]
- [[know-your-agent]]
