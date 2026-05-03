---
title: "Lightspark"
type: company
topic: agentic-money
tags: [infrastructure, wallet, payment-processor, stablecoin, cross-border]
founded:
stage: private
hq: Los Angeles, CA
sources: [Post by @lightspark on X 1.md, Post by @lightspark on X.md, Stripe Is Trying to Make Crypto Disappear.md]
created: 2026-05-03
updated: 2026-05-03
---

# Lightspark

**One-line:** Bitcoin Lightning and stablecoin payment infrastructure company building Grid — a platform for agent-bounded delegation, multi-asset Visa debit cards, and MPP's Bitcoin Lightning integration.

## What they're building

Lightspark's Grid platform is their core product, with three distinct applications:

**1. Grid Global Accounts — Bounded delegation for AI agents**
The first account designed for agents to transact safely. Each agent gets its own operating pocket:
- Funded, scoped, and fully auditable
- Spending limits and approved payees enforced at the wallet level (hard constraints, not soft guardrails)
- Revocable instantly, any time

**2. Visa debit cards backed by stablecoins, Bitcoin, and fiat**
Partnership announced April 30, 2026. Through Grid, financial institutions, fintechs, and businesses can offer Visa debit cards funded by:
- Stablecoins (USDC and others on Solana, Base, and Spark)
- Bitcoin (via Spark or the Lightning Network)
- Fiat (USD, EUR)

Cards usable at 175M+ Visa-accepting merchants worldwide in 100+ countries.

**3. MPP Bitcoin Lightning integration**
[[mpp]] (Stripe's Machine Payments Protocol) supports Bitcoin Lightning payments via Lightspark. This means MPP is rail-agnostic at launch: stablecoin on Tempo, fiat via Shared Payment Tokens, and Bitcoin Lightning via Lightspark.

## Relevance to agentic money

Lightspark sits at two intersections:
1. **Agent delegation infrastructure** — Grid Global Accounts is one of the clearest implementations of bounded agent spending (hard constraints at wallet level), solving what Ramp Labs showed soft guardrails cannot
2. **Bitcoin in the agentic payment stack** — as MPP's Lightning integration partner, Lightspark puts Bitcoin Lightning on the same footing as stablecoin and card payments for machine-to-machine transactions

The Visa card partnership bridges the Lightspark-managed Lightning/stablecoin world to the existing card acceptance network — making on-chain assets spendable at any Visa merchant without requiring merchant-side changes.

## Key people

- **David Marcus** — CEO; previously EVP of Messaging at Facebook, former President of PayPal, former board member of Coinbase; led Meta's Diem project

## Partnerships & integrations

- **[[visa]]** — Visa debit card distribution for stablecoin/Bitcoin-backed cards
- **[[stripe]]/[[mpp]]** — Lightspark is MPP's Bitcoin Lightning rail partner
- **Spark** — Lightspark's Bitcoin protocol (separate from Lightning; Spark and Lightning are both supported as Bitcoin funding sources for the Visa card)

## Open questions

- What is Lightspark's funding stage and latest valuation?
- Is the Spark protocol Lightspark's own Layer 2 or a separate project?
- How does the Visa card product settle — does it convert Bitcoin/stablecoin to fiat at the point of sale, or maintain the asset type?
- What is Lightspark's business model for the Grid Global Accounts product?
- Will Grid Global Accounts support stablecoins beyond USDC?

## Sources

- [[post-lightspark-grid-accounts]] — Grid Global Accounts announcement
- [[post-lightspark-visa-cards]] — Visa partnership announcement
- [[stripe-is-trying-to-make-crypto-disappear]] — MPP + Lightning integration context
