---
title: "Stripe"
type: company
topic: agentic-money
tags: [infrastructure, payment-processor, stablecoin, agentic-commerce]
founded: 2010
stage: private
hq: San Francisco, CA
sources: [Introducing the Machine Payments Protocol.md, Understanding x402 and MPP in One Article Two Routes for Agent Payments.md]
created: 2026-04-25
updated: 2026-04-25
---

# Stripe

**One-line:** Co-authored the Machine Payments Protocol (MPP) with Tempo, launched the Agentic Commerce Suite with live merchant partners, and is positioning as the abstraction layer that lets developers access both x402 and fiat rails through a single API.

## What they're building

Stripe's agentic commerce strategy has three layers:

**1. Machine Payments Protocol (MPP)** — co-authored with [[tempo]], enabling agents to pay for services via sessions (continuous micropayments within an authorized limit) or Shared Payment Tokens (SPTs — user payment credentials passable to agents, scoped to single transactions). Launched March 2026.

**2. Agentic Commerce Suite** — Stripe's broader platform for agentic commerce:
- **Agentic Commerce Protocol (ACP)** — Stripe/OpenAI standard for agent-to-merchant coordination
- MCP integrations for agent tooling
- Live merchant partners: URBN, Etsy, Coach, Kate Spade, Ashley Furniture

**3. Same infrastructure, extended** — All existing Stripe services (tax, fraud protection, reporting, accounting integrations, refunds) work automatically for agent payments. Merchants using Stripe get agent payments "in a few lines of code."

## Relevance to agentic money

Stripe is uniquely positioned: $1.9T in 2025 payment volume (34% YoY growth), deep merchant relationships, and the developer ecosystem that built the modern internet's commerce layer. By owning the abstraction layer above both x402 and fiat rails, Stripe bets that it doesn't matter which protocol wins — developers will route through Stripe regardless.

Key strategic insight from analyst commentary: "Stripe's strategy is to control the abstraction layer and let underlying protocols compete."

## Funding & traction

Private (valued ~$70B). Key MPP metrics at launch (March 2026):
- 34,000 transactions in MPP marketplace's first week
- 100+ services in MPP payment catalog at launch
- Platform integrations: Wix, WooCommerce, BigCommerce, Squarespace, commercetools
- Tempo mainnet partners (at launch): Anthropic, DoorDash, Mastercard, Nubank, OpenAI, Ramp, Revolut, Shopify, Standard Chartered, Visa

## Key people

- Jeff Weinstein — authored MPP announcement
- Steve Kaliski — co-authored MPP announcement

## Products / offerings

- **MPP** — Machine Payments Protocol (co-authored with Tempo)
- **SPT** — Shared Payment Tokens (agent-passable credentials)
- **ACP** — Agentic Commerce Protocol (with OpenAI)
- **Stripe Agentic Commerce Suite** — full suite of agent-ready commerce tools
- PaymentIntents API — extended to support MPP "in a few lines of code"

## Partnerships & integrations

- [[tempo]] — MPP co-author and blockchain settlement layer
- [[ap2]] — AP2 ecosystem partner
- OpenAI — ACP co-author; listed as Tempo mainnet launch partner
- Shopify, DoorDash, Mastercard, Ramp, Revolut, Standard Chartered — Tempo mainnet partners
- Browserbase — using MPP to monetize headless browser sessions (pay-per-session)
- PostalForm — monetizing physical mail services via MPP
- Parallel Web Systems (Parag Agrawal, founder) — early adopter, paying per API call

## Open questions

- Does Stripe want MPP to beat x402, or just to own the layer above both?
- How does ACP (OpenAI/Stripe) differ from AP2 (Google/PayPal) in practice?
- What percentage of Stripe's merchant base is actively using MPP vs. x402?
- Is Tempo a long-term strategic partner or a transitional settlement layer?

## Sources

- [[introducing-the-machine-payments-protocol]]
- [[understanding-x402-and-mpp]]
