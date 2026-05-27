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

## April 2026 updates

UCP added three major capabilities (source: [[commerce-for-ai-brainfood]]):

1. **Cart** — agents can save or add multiple items to a shopping cart from a single store in one action
2. **Catalog** — agents can retrieve real-time product details including variants, inventory, and pricing
3. **Identity Linking** — shoppers receive the same loyalty and member benefits they'd get when logged into a retailer's own site; beginning of a post-purchase trust chain for agents

These updates shift some power from the merchant (who previously "trapped" users in their checkout flow) to the agent (who now brings a signed intent to the merchant, rather than the merchant trapping the user).

**UCP adoption coalition (as of May 2026):** PayPal, Checkout.com, Adyen, Stripe, Visa, Mastercard, and major merchants have backed UCP. Simon Taylor (FintechBrainFood): "UCP is a Trojan horse — it makes merchants and their SKUs headless, enabling agents to securely buy from any UCP-integrated merchant."

**Google Universal Cart (Google I/O, May 2026):** Google announced a Universal Shopping Cart that follows users across Search, YouTube, and Gmail. Identifies incompatible items. Notifies on price drops and restocks. Rolls out summer 2026 in the US via Search and Gemini. UCP is the protocol making this possible beyond Google surfaces.

## Live implementations

- **Google Search AI Mode** — Native Checkout for qualifying merchants
- **Google Gemini** — Shopping via UCP (Etsy, Wayfair confirmed)

## Google I/O 2026 launch (May 2026)

Source: [[introducing-universal-cart]] (Vidhya Srinivasan, 2026-05-19)

**Confirmed merchants at launch:** Nike, Sephora, Target, Ulta Beauty, Walmart, Wayfair, Fenty (via Shopify), Steve Madden (via Shopify)

**Geographic expansion:** Canada and Australia in coming months, then UK

**Surface expansion:** YouTube (US) coming soon; Gmail to follow

**Vertical expansion:** Hotel booking and local food delivery coming soon

**UCP GitHub:** New tech partners welcomed to steer the open standard — UCP is formally open for external contribution

## Significance

UCP positions Google as the commerce discovery layer for the agentic web, parallel to how Google Search dominated web discovery for humans. If UCP becomes the standard for agent-to-merchant communication, Google controls the top of the agentic commerce funnel.

## Primary source

Published January 2026. Spec available at [developers.google.com/merchant/ucp](https://developers.google.com/merchant/ucp).

## Related concepts

- [[ap2]]
- [[agentic-commerce]]
- [[know-your-agent]]
