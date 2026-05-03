---
title: "Stripe Is Trying to Make Crypto Disappear"
type: summary
topic: agentic-money
source_type: social
tags: [infrastructure, stablecoin, payment-processor, agentic-commerce, compliance]
sources: [Stripe Is Trying to Make Crypto Disappear.md]
created: 2026-05-03
updated: 2026-05-03
---

# Stripe Is Trying to Make Crypto Disappear

**Source:** [@snapcrackle on X](https://x.com/snapcrackle/status/2050910293597856077), published 2026-05-03
**Format:** Deep-dive research thread (~5,000 words); author discloses no commercial relationship with any named company.

## Core thesis

Stripe is not making a crypto bet. It is making crypto invisible — burying stablecoin infrastructure so deeply inside enterprise payment plumbing that merchants, consumers, and agents never have to say "wallet," "gas," "bridge," "validator," or "chain." The stablecoin is there. The blockchain is there as plumbing.

Secondary observation: [[circle]] independently arrived at almost exactly the same architecture with [[circle-arc]]. Two dominant companies converging on a permissioned-L1 design is stronger evidence of a market category than either company alone.

---

## The stack Stripe assembled

| Layer | Product | Route |
|-------|---------|-------|
| Settlement chain | [[tempo]] | Cofounded (Tempo Labs, Delaware C-corp, filed May 2025) |
| Stablecoin orchestration + issuance | [[bridge]] | Acquired October 2024, $1.1B |
| Developer wallet infrastructure | Privy | Acquired June 2025, ~$230M prior private valuation |
| Mobile payments team | Valora team (ex-cLabs) | Acquired December 2025; app/IP returned to cLabs |
| Consumer wallet | Link | Organic; holds stablecoins for 250M consumers |
| Machine payment protocol | [[mpp]] | Coauthored with [[tempo]] |
| Federal trust charter | Bridge National Trust Bank | OCC conditional approval Feb 2026 |
| Fiat payment volume | Stripe core | $1.9T payment volume in 2025 (+34% YoY) |

Merchants see Stripe Balance. Consumers see Link. Neither surface shows a wallet, address, or chain.

---

## Why Tempo exists

During a memecoin frenzy on a major blockchain, a Bridge customer waited more than 12 hours for a payout while per-transaction costs spiked 35x. This crystallized the need for a settlement layer isolated from consumer speculation — one with predictable performance and fees for institutional payment flows.

Stripe's three options: build on Ethereum (congestion risk), build on Solana (speculation still leaks), or build something purpose-built. They chose the third, in partnership with Paradigm.

**Tempo's payments-first design choices:**
- No native token — no separate asset needed before using the chain
- Stablecoin-native gas — fees paid in the same unit as the payment
- Dedicated blockspace lanes — prevents memecoin-congestion scenario from repeating
- ISO 20022-aligned memos — for ERP reconciliation
- Fee AMM — auto-converts stablecoin gas to validator's preferred stablecoin
- Optional privacy with compliance blocklists
- **Tempo Zones** — private EVM-compatible chains parallel to mainnet for enterprise use cases (payroll, compliance, agent-scale microtransactions)

Validators as of mid-April 2026: ~11 total; Visa, Stripe, and Zodia Custody (Standard Chartered majority-owned) announced as first external validators on April 14, 2026.

**Analyst prediction:** The agent-scale microtransaction layer ships under Tempo Zones, not as a separate rollup brand. Watch for AI-agent-focused Zones with OpenAI or Anthropic as first announced operator.

---

## MPP and the control plane

MPP builds on x402's HTTP 402 handshake but adds four production features x402 currently lacks:
1. First-class idempotency
2. Request-body digest binding
3. Credential expiration
4. Structured receipts

Plus a pre-funded session model: an agent deposits once and spends against balance via off-chain vouchers settled in batches. This is Lightning for stablecoins, enabled by Tempo's one-way payment channel primitive at L1 (built by Liam Horne, former Optimism CEO, on the Tempo team). Makes token-streaming and per-inference billing viable at scale.

Rail-agnostic at launch: stablecoin payments on Tempo; fiat methods via Shared Payment Tokens; Bitcoin Lightning via [[lightspark]]. Visa has published a card-based MPP extension.

**The interchange preservation argument:** When an agent pays via MPP with a Shared Payment Token, interchange is preserved and Stripe stays in the flow. When an agent pays via MPP with stablecoin, settlement happens on Tempo — still touching Stripe's balance sheet. Either way, Stripe is not disintermediated. Stablecoin payments bypass card networks; MPP preserves the card path as an option.

**IETF submission:** MPP submitted as a proposed IETF payment authentication scheme.

---

## The Bridge thesis and OCC charter

**Open Issuance platform (launched September 2025):** Rather than absorbing reserve yield, Bridge shares the majority with issuers (Phantom, Klarna, Hyperliquid, MetaMask). This is app-store economics for stablecoins — the platform where coins are launched, custodied, swapped, reconciled, and regulated. Stripe extracts a take rate on the float rather than processing fees.

**Bridge National Trust Bank (OCC conditional approval, February 2026):** Conditions include $45M Tier 1 capital, capital raised within 12 months, bank open within 18. Stated purpose: issue stablecoins, be primary issuer of xUSD, provide custody for affiliates and unaffiliated institutional customers.

Most coverage missed this: Bridge is not applying to hold Stripe's own reserves. It is applying to be the bank other people custody through. Michael Lempres (former Coinbase CLO, former Asst. Secretary of Defense) is an organizer — that CV points to a platform build, not a treasury function.

**Analyst prediction:** Within 18 months of final approval, Bridge applies for expanded OCC authorities to custody stablecoin reserves for third-party fintechs.

Structural note: a national trust charter does not make Stripe a bank holding company under the Bank Holding Company Act. Stripe gets federal regulatory legitimacy without becoming bank-regulated.

---

## GENIUS Act regulatory shaping

Two GENIUS Act details that shaped Stripe's architecture:

1. Bars non-financial public companies from issuing stablecoins directly without unanimous three-agency committee approval — making Meta's Diem path prohibitively expensive. Stripe is reportedly the leading candidate for Meta's stablecoin partnership. Mark Zuckerberg, on stage at Stripe Sessions 2025 with John Collison: "You guys are probably the much better company to do this."

2. OCC proposed rule (March 2026) distinguishes B2B yield-sharing (allowed, protects Bridge's Open Issuance model) from consumer-facing yield programs passed through affiliated intermediaries (targeted). Bridge sharing yield with Klarna (non-affiliate) is explicitly protected. Coinbase's USDC rewards model needs restructuring.

Stripe hired Cornerstone Washington for its GENIUS Act lobbying cycle — a firm that specializes in financial services regulatory carve-outs.

---

## The self-disruption bet

Stablecoin payments on Tempo bypass card interchange. Stripe is building the thing that, if it succeeds, hollows out the business model that funded its construction. The counter: either a card token (interchange preserved, Stripe earns existing fee) or a stablecoin (settles on Tempo, touches Bridge + Tempo + Stripe balance). Whichever rail wins, the payment ends inside a system Stripe owns.

---

## Sessions 2026 signals

- AI agent traffic to Stripe docs: <5% → ~40% of total docs traffic in 2025
- Sam Altman cited Stripe explicitly as the template for OpenAI's "forever low-margin infrastructure provider" model
- Will Gaybrick demonstrated live streaming payments settling thousands of sub-cent stablecoin transactions on Tempo Block Explorer
- Shopify announced joining Tempo validator set
- Klarna USD live as Bridge-issued branded stablecoin
- Farcaster founders Dan Romero + Varun Srinivasan joined Tempo Feb 2026 — signals an agent identity/social graph layer

---

## The Circle mirror

Tempo and Arc are architecturally convergent:
- Permissioned L1 with named financial-institution validators
- Stablecoin-native unit of account
- Sub-second finality
- Privacy primitives
- B2B payment reliability as design target

**Strategic divergence:** Circle accumulates policy-legitimacy capital (Davos, IMF, central bank panels). Stripe accumulates developer and enterprise distribution (Stripe Sessions). When the next stablecoin regulatory framework is written in Brussels or Singapore, Jeremy Allaire will be in the room; the Collisons likely won't be.

Two arriving at the same architecture independently validates a market category, not just a product.

---

## Where the bet could break

1. Ethereum's rollup ecosystem matures before Tempo reaches institutional adoption
2. Regulatory concentration risk — owning issuance, orchestration, wallet, settlement, and charter inside one structure
3. Matt Huang's triple role (Stripe board + Paradigm managing partner + Tempo CEO) creates institutional governance questions; Henri Stern (Privy CEO) publicly flagged the 2–3 year decentralization question on Stripe's own podcast
4. Mastercard's $1.8B BVNK acquisition (direct Bridge competitor) may signal weakening consortium loyalty — **prediction:** Mastercard quietly exits Tempo design partner list within 12 months

---

## Related pages

- [[tempo]] — the settlement chain
- [[bridge]] — stablecoin orchestration + issuance subsidiary
- [[mpp]] — Machine Payments Protocol
- [[circle]] — parallel architecture via [[circle-arc]]
- [[lightspark]] — MPP's Bitcoin Lightning partner
- [[stablecoin]] — the money layer
- [[giving-agents-the-ability-to-pay]] — Link's wallet for agents (Stripe blog, April 29)
