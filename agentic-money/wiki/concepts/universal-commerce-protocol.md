---
title: "Universal Commerce Protocol (UCP)"
type: concept
topic: agentic-money
tags: [infrastructure, agentic-commerce, identity-kyc]
sources: [2957-4390-068.2026.issue-004-en.pdf, AI at the Checkout > AI is the Checkout.md]
created: 2026-04-26
updated: 2026-05-03
---

# Universal Commerce Protocol (UCP)

**One-line:** The open standard that every major hyperscaler, commerce platform, and payments network has now adopted — standardizing how AI agents interact with merchant backends for discovery, negotiation, transaction, and fulfillment, while keeping the merchant in control of their checkout.

## What it is

UCP is a layered commerce protocol — not a payment protocol. It covers everything before and after the payment:

1. **Discovery** — agents query a merchant's `/.well-known/ucp` manifest to find capabilities (loyalty programs, catalogs, pre-orders)
2. **Negotiation** — real-time pricing, tax, and discount stacking via standardized APIs
3. **Transaction** — API-driven checkout sessions; uses [[ap2]] for verified, one-tap payment authorization
4. **Fulfillment & Settlement** — logistics orchestration (shipping vs. pickup), post-purchase status updates

**Layered like TCP/IP:**
- Core checkout primitives at the bottom
- Capabilities (Catalog, Orders, Checkout) above
- Extensions (loyalty, fulfillment, subscriptions) compose on top

Merchants implement only what they need. Anyone with a namespace (their .com) can extend the protocol without permission. This open architecture is why every PSP, commerce platform, and hyperscaler eventually converged on it.

## The UCP Tech Council expansion (April 24, 2026)

Amazon, Meta, Microsoft, Salesforce, and Stripe joined the UCP Tech Council. They join Google, Shopify, Etsy, Target, and Wayfair.

The combined roster now covers:
- Every major hyperscaler
- Every major commerce platform in the transatlantic sphere
- All major PSPs (Stripe, Adyen, Checkout.com)
- All major marketplaces (Etsy, Wayfair, Target, Walmart, Best Buy, Home Depot, Macy's, Flipkart, Zalando)
- Card schemes (Visa, Mastercard, Amex)

**This is the first time the agentic commerce category has agreed on anything.**

## UCP vs. ACP: what the data shows

| | **UCP** | **ACP** |
|---|---|---|
| Philosophy | Merchant owns checkout | AI/chatbot owns checkout |
| Originating partnership | Google + Shopify | OpenAI + Stripe |
| Starting point | Full commerce flow → refined to checkout | Checkout → worked outward |
| Status (May 2026) | Industry coalition standard | Evolved toward merchant-owned model |

**The Walmart validation:**

*Test 1 — ChatGPT Instant Checkout (ACP-style, AI-owned):*
Walmart tested 200,000 SKUs. Conversion: one-third of click-out rates. Daniel Danker (Walmart EVP): "unsatisfying." OpenAI closed Instant Checkout two weeks later.

*Test 2 — Sparky (UCP-style, merchant-owned):*
Walmart embedded Sparky inside its own app, keeping cart and checkout on Walmart.com:
- Half of Walmart app users engaged with Sparky
- Sparky users: AOV **35% higher** than non-Sparky users
- Sparky inside ChatGPT: converts at **~70% of Walmart.com direct** rates — 2x ChatGPT Instant Checkout's run rate

The pattern is consistent: AI by the merchant can work. AI by the aggregator doesn't yet.

Additional data points:
- Tatcha (Unilever): on-site AI drives 11.4% of total site revenue, 3x conversion rate, AOV +38%
- Microsoft Copilot Checkout: 53% more purchases within 30 minutes when shopping intent is present
- Adobe (2025 holiday): AI-driven traffic +693% YoY; AI referrals now convert 31% better than other channels

## How UCP fits in the protocol stack

UCP is one layer among several:

| Layer | Protocol | Owner |
|-------|---------|-------|
| Agent communication | A2A | Google |
| Mandate / authorization | [[ap2]] | Google |
| Commerce / transaction coordination | UCP | Google + Shopify (open) |
| Machine payments (API resources) | [[mpp]], [[x402]] | Stripe/Tempo, Coinbase |
| Payment rails | Cards, ACH, stablecoins | Existing networks |

MPP and x402 solve agent-to-API micropayments; UCP solves agent-to-merchant commerce. These are different layers for different purposes.

## The container metaphor

> "Before containers, global trade existed, but every handoff was bespoke. The container standardized the interface — it did not own the goods. UCP is the container for agentic commerce."
> — @sytaylor

## Primary source

Co-developed by Google and Shopify. Spec at [developers.google.com/merchant/ucp](https://developers.google.com/merchant/ucp). Published January 2026.

## Related concepts

- [[ap2]] — authorization and mandate layer
- [[agentic-commerce]] — the broader category UCP enables
- [[acp]] — OpenAI's competing then converging standard
- [[mpp]], [[x402]] — machine payment protocols (different layer)
- [[ai-at-the-checkout]] — summary of @sytaylor analysis including Walmart data
