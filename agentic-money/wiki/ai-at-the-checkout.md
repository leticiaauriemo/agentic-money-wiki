---
title: "AI at the Checkout > AI is the Checkout"
type: summary
topic: agentic-money
source_type: analysis
tags: [agentic-commerce, infrastructure]
sources: [AI at the Checkout > AI is the Checkout.md]
created: 2026-05-03
updated: 2026-05-03
---

# AI at the Checkout > AI is the Checkout

**Source:** [@sytaylor on X](https://x.com/sytaylor/status/2050906143044641149), published 2026-05-03
**Author:** Simon Taylor (@sytaylor), writes Fintech Brainfood newsletter
**Format:** Long-form analysis thread / article

## Core finding

After two years of agent checkout experiments, the market has found its answer: **the merchant owns the checkout, not the AI**. The data from live experiments is now in, and merchant-owned AI consistently outperforms AI-owned checkout.

---

## The UCP Tech Council moment (April 24, 2026)

Amazon, Meta, Microsoft, Salesforce, and Stripe joined the [[universal-commerce-protocol]] (UCP) Tech Council.

They join: Google, Shopify, Etsy, Target, and Wayfair.

The combined roster covers:
- Every major hyperscaler
- Every major commerce platform
- Every payments network of relevance in the transatlantic sphere

Card schemes (Visa, Mastercard, Amex), PSPs (Stripe, Adyen, Checkout), marketplaces (Etsy, Wayfair, Target, Walmart, Best Buy, Home Depot, Macy's, Flipkart, Zalando).

**This is the first time the agentic commerce category has agreed on anything.**

---

## What UCP is (and isn't)

UCP is not a payment protocol. It is a commerce protocol — everything before and after the transaction.

**UCP's four layers:**
1. **Discovery** — agents query a merchant's `/.well-known/ucp` manifest to find capabilities (loyalty programs, catalogs, pre-orders)
2. **Negotiation** — real-time pricing, tax, discount stacking via standardized APIs
3. **Transaction** — API-driven checkout sessions via Agent Payments Protocol (AP2) for verified checkout
4. **Fulfillment & Settlement** — logistics orchestration, post-purchase status updates

**Layered like TCP/IP:**
- Core checkout primitives at the bottom
- Capabilities (Catalog, Orders, Checkout) above
- Extensions (loyalty, fulfillment, subscriptions) compose on top

Merchants implement only what they need. Anyone with a namespace (their .com or equivalent) can extend the protocol without permission. This architecture is why every PSP, every commerce platform, and every hyperscaler eventually converged on it.

---

## UCP vs. ACP: merchant-owned won

| | **UCP** | **ACP** |
|---|---|---|
| **Philosophy** | Merchant owns checkout | AI/chatbot owns checkout |
| **Co-developed by** | Google + Shopify | OpenAI + Stripe |
| **Starting point** | Full commerce flow, worked inward | Checkout first, worked outward |
| **Status (May 2026)** | Industry coalition, dominant | Evolved toward merchant-owned model |

ACP (OpenAI's Agentic Commerce Protocol) began with Instant Checkout inside ChatGPT and worked outward. UCP started with the merchant's full commerce flow. Today the two specs are converging — the path ACP took is the key distinction.

---

## The Walmart experiment

**Test 1 — ChatGPT Instant Checkout (ACP-style, AI-owned checkout):**
- 200,000 SKUs tested through ChatGPT Instant Checkout
- Conversion: **one third of click-out rates**
- Daniel Danker (Walmart's EVP of AI Acceleration, Product and Design): "unsatisfying"
- Two weeks later: OpenAI announced closure of Instant Checkout

**Test 2 — Sparky (merchant-owned AI):**
- Walmart embedded Sparky inside its app (and later as a ChatGPT app), keeping cart, login, and checkout on Walmart.com
- Results from Walmart Q4 FY26 earnings call:
  - Half of Walmart's app users have engaged with Sparky
  - Sparky users: average order value **35% higher** than non-Sparky users
  - Sparky inside ChatGPT: converts at **~70% of Walmart.com direct** rates — more than double ChatGPT Instant Checkout's run rate

**The takeaway:** "AI by the merchant can work. AI by the aggregator doesn't yet."

---

## Broader conversion data

| Source | Signal |
|--------|--------|
| University of Hamburg study (973 e-comm sites, 50K ChatGPT txns) | ChatGPT referrals underperform all channels except paid social; 0.2% of total traffic; affiliate links convert 86% better |
| Adobe (2025 holiday season) | AI-driven retail traffic +693% YoY; AI referrals now convert 31% better than other channels (vs. 9% *worse* three months prior) |
| Shopify (Q4 2026 earnings) | AI-attributed orders grew 15x since start of 2025 |
| Panxo | ChatGPT converts at 11.4%, beating direct, paid search, organic, email |
| Tatcha (Unilever) | On-site AI: 11.4% of total site revenue; 3x site average conversion; AOV +38% |
| Microsoft Copilot Checkout | 53% more purchases within 30 minutes when shopping intent is present |

Two things are simultaneously true: AI-referred traffic is growing fast off a tiny base; the mainstream is not yet here.

---

## The agentic commerce protocol stack

UCP is not the whole stack — it is one layer:

| Layer | Protocol | Owner |
|-------|---------|-------|
| Agent communication | A2A | Google |
| Mandate / authorization | AP2 | Google |
| Commerce / transaction coordination | UCP | Google + Shopify (open) |
| Machine payments (API resources) | [[mpp]], [[x402]] | Stripe/Tempo, Coinbase |
| Payment rails | Cards, ACH, stablecoins | Existing |

MPP and x402 solve agent-to-API payments. ACP and UCP solve agent-to-merchant commerce. These are different problems.

---

## Open questions merchants face

- **Fraud:** No data yet on whether agentic commerce is better or worse; schemes building frameworks
- **Returns:** Transaction volumes still too small for return-rate signals; liability question unresolved (Target says user is liable for agent purchases)
- **Attribution:** UCP/ACP webhooks tell merchants what sold and which agent sold it, but nothing about discovery, consideration, or incrementality

---

## The strategic implication

The gap between early-adopter merchants and laggards is about to widen. Merchants who run 20 UCP experiments in 2026 will have a data advantage when AI conversion exceeds e-commerce checkout conversion. AI adoption is near-universal; AI value capture is concentrated in a small minority. The 1% getting gains now will define the playbook.

---

## Related pages

- [[universal-commerce-protocol]] — the UCP standard
- [[acp]] — OpenAI's competing standard
- [[ap2]] — Google's mandate/authorization layer
- [[mpp]], [[x402]] — machine payment protocols (different layer)
- [[stripe]] — joined UCP Tech Council; also ACP co-author
- [[paypal]] — agentic commerce layer via ACP
