---
title: "Understanding x402 and MPP in One Article: Two Routes for Agent Payments"
type: summary
topic: agentic-money
source_type: analysis
tags: [infrastructure, agentic-commerce, crypto-l2, payment-processor]
sources: ["Understanding x402 and MPP in One Article Two Routes for Agent Payments.md"]
created: 2026-04-25
updated: 2026-04-25
---

# Understanding x402 and MPP in One Article: Two Routes for Agent Payments

**Source:** [RootData / defiprime.com](https://www.rootdata.com/news/584290)
**Author:** Nick Sawinyh (defiprime.com), translated by Peggy (Blockbeats)

## Core argument

x402 and MPP represent opposite philosophical approaches to the same problem — they aren't in direct competition but serve different markets. x402 is minimalist and permissionless; MPP is feature-rich and compliance-oriented.

## Side-by-side comparison

| Dimension | x402 | MPP |
|-----------|------|-----|
| Philosophy | Minimalist, embed payments in HTTP | Maximal, sessions + streaming + fiat |
| Launch | May 2025 (Coinbase) | March 2026 (Stripe + Tempo) |
| Governance | x402 Foundation (Coinbase, Cloudflare, Sep 2025) | Open standard spec |
| Payment types | Per-call stablecoin | Charge (per-call) + Session (metered) |
| Fiat support | No | Yes (Stripe cards) |
| Partners | Coinbase, Cloudflare, Google, Visa, World | Anthropic, DoorDash, Mastercard, Nubank, OpenAI, Ramp, Revolut, Shopify, Standard Chartered, Visa |
| Target | Long-tail open networks | Enterprise/high-frequency |

## Key historical context

The HTTP 402 status code ("Payment Required") was reserved in the HTTP/1.1 specification in the 1990s — approximately 27 years waited unused before x402 gave it a purpose.

## Stripe's strategic position

Stripe supports both protocols and abstracts the layer above, ensuring funds flow into Stripe regardless of which protocol wins. The article estimates: if both protocols scale, Stripe is indifferent to which one dominates.

## Current state (as of April 2026 snapshot)

Almost no truly scaled transactions exist — most activity is experimental or in testing phase. The article estimates x402 daily volume at ~131,000 transactions and ~$28,000 total, with ~50% appearing to be testing or gamified.

> **Note (2026-04-25):** The $49.51M all-time volume from [[x402]] dashboard is the authoritative figure. The $28K daily figure above likely reflects a point-in-time snapshot.

## MPP ecosystem at launch

100+ services in MPP payment catalog at launch: Alchemy, Dune Analytics, Merit Systems, Parallel Web Systems. Tempo supports 10,000+ TPS with sub-second confirmations.

## Related pages

- [[x402]]
- [[mpp]]
- [[tempo]]
- [[stripe]]
- [[coinbase]]
