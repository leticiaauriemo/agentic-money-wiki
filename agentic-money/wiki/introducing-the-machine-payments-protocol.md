---
title: "Introducing the Machine Payments Protocol"
type: summary
topic: agentic-money
source_type: company-blog
tags: [infrastructure, stablecoin, agentic-commerce, payment-processor]
sources: [Introducing the Machine Payments Protocol.md]
created: 2026-04-25
updated: 2026-04-25
---

# Introducing the Machine Payments Protocol

**Source:** [Stripe Blog, 2026-03-18](https://stripe.com/blog/machine-payments-protocol)
**Authors:** Jeff Weinstein, Steve Kaliski (Stripe)

## Key argument

Current financial systems were built for humans. AI agents can't create accounts, navigate pricing pages, choose subscriptions, enter payment details, or set up billing without human intervention. MPP fixes this by enabling agents and services to coordinate payments programmatically at the protocol level.

## How MPP works

**Two payment intents:**
1. **Charge** — one-time payment per request (~500ms latency); best for API calls, content access
2. **Session** — continuous pay-as-you-go within an authorized spending limit; near-zero latency per call; best for LLM APIs and metered services

**Shared Payment Tokens (SPTs):** User payment credentials (credit card or wallet) that can be passed to agents, scoped to a single transaction with time constraints. Agents can pay via USDC on Tempo or user-linked Visa card via SPT.

**Integration:** Stripe users accept MPP via PaymentIntents API in "a few lines of code." All existing Stripe infrastructure (tax, fraud, reporting, refunds) applies automatically to MPP payments.

## Live at launch (March 2026)

- **Browserbase** — monetizing headless browser sessions (pay-per-session)
- **PostalForm** — monetizing physical mail services via MPP
- **Parallel Web Systems** (Parag Agrawal, founder) — paying per API call
- 100+ services in MPP payment catalog

**Broader Stripe agentic commerce strategy:**
- Agentic Commerce Protocol (ACP) — co-developed with OpenAI
- Agentic Commerce Suite — live merchant partners: URBN, Etsy, Coach, Kate Spade, Ashley Furniture
- MCP integrations

## Key insight

MPP vs. x402 strategic difference: x402 is minimalist and open (Unix philosophy); MPP is orchestrated and enterprise-grade. Stripe's bet is that it controls the abstraction layer — letting x402 and MPP compete below while developers use Stripe's unified API above.

## Stats

- Stripe 2025 payment volume: $1.9 trillion (34% YoY growth)
- MPP marketplace: 34,000 transactions in first week
- McKinsey: agentic commerce will mediate $3–5 trillion of global commerce by 2030

## Related pages

- [[mpp]]
- [[stripe]]
- [[tempo]]
- [[x402]]
- [[understanding-x402-and-mpp]]
