---
title: "Stripe"
type: company
topic: agentic-money
tags: [infrastructure, payment-processor, stablecoin, agentic-commerce, wallet]
founded: 2010
stage: private
hq: San Francisco, CA
sources: [Introducing the Machine Payments Protocol.md, Understanding x402 and MPP in One Article Two Routes for Agent Payments.md, Stripe Is Trying to Make Crypto Disappear.md, Giving agents the ability to pay.md]
created: 2026-04-25
updated: 2026-05-03
---

# Stripe

**One-line:** The most vertically integrated player in agentic payments — owning settlement chain (Tempo), stablecoin issuance (Bridge), developer wallets (Privy), consumer wallet (Link, 250M users), machine payment protocol (MPP), and a pending federal trust bank charter — positioned to make crypto invisible inside enterprise payment infrastructure.

## The thesis @snapcrackle

Stripe is not making a crypto bet. It is making crypto disappear — burying stablecoin infrastructure so deeply inside enterprise payment plumbing that merchants, consumers, and agents say neither "wallet," "gas," "bridge," nor "chain." Merchants see Stripe Balance. Consumers see Link. Neither surface shows blockchain primitives.

Sam Altman, on stage with Patrick Collison at Sessions 2026: he would like OpenAI "to be a forever low-margin infrastructure provider" and cited Stripe explicitly as the template. The most influential AI lab has publicly chosen not to compete with Stripe at the payments layer.

## The stack

| Layer | Product | Route |
|-------|---------|-------|
| Settlement chain | [[tempo]] | Cofounded (Tempo Labs, Delaware C-corp, May 2025) |
| Stablecoin orchestration + issuance | [[bridge]] | Acquired October 2024, $1.1B |
| Developer wallet infrastructure | Privy | Acquired June 2025, last private valuation ~$230M |
| Mobile payments team | Valora team (ex-cLabs) | Acquired December 2025; app/IP returned to cLabs |
| Consumer wallet | Link | Organic; 250M consumers; holds stablecoins |
| Machine payment protocol | [[mpp]] | Coauthored with [[tempo]] |
| Federal trust charter | Bridge National Trust Bank | OCC conditional approval Feb 2026 |
| Fiat rail | Stripe core | $1.9T payment volume 2025 (+34% YoY) |

## Products (agentic focus)

**1. Machine Payments Protocol (MPP)**
Co-authored with [[tempo]]. Two modes: Charge (per-call, ~500ms) and Session (authorize-once, continuous micropayments via off-chain vouchers). Rail-agnostic: stablecoin on Tempo, fiat via Shared Payment Tokens (SPTs), Bitcoin Lightning via [[lightspark]]. IETF submission. See [[mpp]].

**2. Link's wallet for agents** (launched April 29, 2026)
Consumer-facing: personal AI agents get programmatic access to the Link wallet (250M consumers) via OAuth grant → spend request → one-time card or SPT returned after consumer approval. Agent never sees raw payment credentials. Scoped by amount, currency, merchant. Built on Stripe Issuing for agents.

**3. Stripe Issuing for agents**
Developer-facing API layer for businesses building custom agentic wallets and cards. Full Issuing API access, single-use virtual cards, spending controls, fraud tools, real-time visibility.

**4. Shared Payment Tokens (SPTs)**
User payment credentials passable to agents, scoped to single transactions; preserves interchange when used with MPP.

**5. Agentic Commerce Suite**
Full agent commerce platform: MPP, SPTs, MCP integrations, live merchant partners (URBN, Etsy, Coach, Kate Spade, Ashley Furniture).

**6. Stripe Balance**
Merchant-side stablecoin balance — the business-facing surface that makes crypto invisible.

## The self-disruption bet

Stablecoin payments on Tempo bypass card interchange. Stripe is building the thing that, if it succeeds, hollows out the card fee business that funded its construction. The counter: whether an agent pays via MPP with an SPT (interchange preserved, Stripe earns existing fee) or via MPP with stablecoin (settles on Tempo, touches Bridge + Tempo + Stripe balance), the payment ends inside a system Stripe owns. The pivot happens inside Stripe's own architecture.

## GENIUS Act regulatory positioning

1. **Non-financial public companies barred from issuing stablecoins directly** → Meta's Diem path became prohibitively expensive → Stripe is reported as the leading candidate for Meta's stablecoin partnership
2. Mark Zuckerberg at Stripe Sessions 2025 (on Diem): "You guys are probably the much better company to do this"
3. **OCC proposed rule (March 2026)** explicitly protects B2B yield-sharing (Bridge's Open Issuance model) while targeting consumer-facing yield programs (Coinbase USDC rewards model)
4. Stripe hired Cornerstone Washington for GENIUS Act lobbying — a financial services regulatory carve-out firm

Stripe's position (B2B infrastructure, non-affiliate yield-sharing, trust charter over bank charter) is GENIUS-aligned by construction.

## Key Sessions 2026 signals

- AI agent traffic to Stripe docs: <5% → ~40% of total traffic in 2025
- Will Gaybrick demonstrated live streaming payments settling thousands of sub-cent stablecoin transactions on Tempo Block Explorer
- Shopify announced joining Tempo validator set
- Klarna USD live as Bridge-issued branded stablecoin
- Farcaster founders joined Tempo (identity layer signal)

## Key people

- **Patrick Collison** — CEO, co-founder
- **John Collison** — President, co-founder; at Sessions 2025 with Zuckerberg
- **Matt Huang** — Tempo CEO + Stripe board member + Paradigm managing partner; triple role is being monitored by institutional counterparties
- **Henri Stern** — Runs Privy inside Stripe; publicly flagged the Tempo decentralization question on Stripe's own podcast
- **Jeff Weinstein** — authored MPP announcement
- **Steve Kaliski** — co-authored MPP announcement
- **Dan Hill** — authored Link's wallet for agents announcement

## Acquisitions

- **[[bridge]]** (October 2024, $1.1B) — stablecoin orchestration + Open Issuance + OCC trust bank charter
- **Privy** (June 2025, undisclosed; ~$230M prior valuation) — 110M programmable wallets; Shamir's Secret Sharing; chain-agnostic
- **Valora team** (December 2025) — mobile stablecoin engineers from cLabs (app/IP returned to cLabs on acquisition)

**Privy note:** Privy behaves as chain-agnostic rather than a pure Tempo feeder. In September 2025, Privy partnered with AllUnity to power EURAU (first euro stablecoin licensed as electronic money under German BaFin) — a competing euro stablecoin to anything Bridge might eventually issue. Bridge is Stripe's bet; Privy is the hedge.

## Funding & traction

- Private, valued ~$70B
- $1.9T payment volume in 2025 (+34% YoY)
- 5M businesses in 195 countries
- 99.999% uptime
- 250M Link consumers
- 34,000 MPP transactions in first week of marketplace

## Partnerships & integrations

- [[tempo]] — MPP co-author and settlement chain
- [[bridge]] — stablecoin issuance subsidiary
- [[lightspark]] — MPP's Bitcoin Lightning rail
- [[visa]] — anchor validator on Tempo; MPP card extension author
- [[universal-commerce-protocol]] — joined UCP Tech Council April 24, 2026
- OpenAI — Sam Altman cited Stripe as template; ACP co-author; Tempo design partner
- Shopify, DoorDash, Mastercard, Nubank, Revolut, Standard Chartered — Tempo mainnet launch partners
- Browserbase, PostalForm, Parallel Web Systems (Parag Agrawal) — MPP early adopters
- Platform integrations: Wix, WooCommerce, BigCommerce, Squarespace, commercetools

## Open questions

- Does the Meta stablecoin partnership materialize? If so, what does Bridge's issuance role look like?
- When does Tempo's validator set decentralize to the point institutional counterparties are satisfied?
- How does Privy's chain-agnostic positioning coexist with Bridge's Tempo-centric orbit long-term?
- Will x402 and MPP converge at the x402 Foundation level, and on what timeline?

## Sources

- [[introducing-the-machine-payments-protocol]]
- [[understanding-x402-and-mpp]]
- [[stripe-is-trying-to-make-crypto-disappear]]
- [[giving-agents-the-ability-to-pay]]
- [[the-new-stack-for-global-finance-stablecoins]]
