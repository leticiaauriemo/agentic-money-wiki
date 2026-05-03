---
title: "Tempo"
type: company
topic: agentic-money
tags: [stablecoin, infrastructure, payment-processor, agentic-commerce, cross-border, crypto-l1]
founded: 2025
stage: private
hq: Delaware (US)
sources: [What are stablecoins? ⋅ Tempo 1.md, Stripe Is Trying to Make Crypto Disappear.md, Post by @0xSammy on X.md]
created: 2026-04-25
updated: 2026-05-03
---

# Tempo

**One-line:** A purpose-built payments L1 blockchain, cofounded by Stripe and Paradigm, designed to run institutional stablecoin payments at scale — isolated from consumer speculation, compatible with enterprise compliance requirements, and already carrying live production traffic from Visa, Stripe, and Standard Chartered.

## What they're building

Tempo is an EVM-compatible Layer-1 blockchain built specifically for payment settlement, not general-purpose DeFi or consumer crypto. Every design choice optimizes for institutional payment reliability:

- **No native token** — no separate asset to acquire before using the chain; gas paid in stablecoin
- **Stablecoin-native gas** — fees in the same unit as the payment being settled
- **Dedicated blockspace lanes** — reserves capacity for payments; memecoin-speculative traffic cannot crowd out settlement
- **ISO 20022-aligned memos** — ERP reconciliation compatible
- **Fee AMM** — auto-converts stablecoin gas to each validator's preferred stablecoin
- **Optional privacy with compliance blocklists** — enterprise-compatible
- **One-way payment channel primitive at L1** — enables the [[mpp]] pre-funded session model (off-chain vouchers settled in batches); Lightning for stablecoins
- **Tempo Zones** — private EVM-compatible chains parallel to mainnet; designed for enterprise use cases (payroll, compliance, agent-scale microtransactions) where operators need controlled execution domains

**Throughput target:** 100K+ TPS with sub-second finality (public). The actual architecture is unlimited off-chain throughput inside Zones, batched and settled to mainnet for the audit trail.

## Why Tempo was built

Trigger event: during a memecoin trading frenzy on a major public blockchain, a Bridge (Stripe's stablecoin subsidiary) customer waited more than 12 hours for a payout while per-transaction costs spiked 35x. The conclusion: institutional payment flows cannot share blockspace with consumer speculation.

Stripe's three options: Ethereum (congestion and fee unpredictability), Solana (speculation still leaks into enterprise settlement), or purpose-built. They chose purpose-built, in partnership with Paradigm.

## Governance structure and validator set

**Entity:** Tempo Labs, Inc. — Delaware C-corp filed May 2025.

**Validators (as of mid-April 2026):** ~11 total. Most operated by Tempo itself. External validators announced April 14, 2026: **Visa**, **Stripe**, **Zodia Custody** (Standard Chartered's majority-owned custodian). No staking requirement. Validators selected by Tempo-controlled multisig.

**Significance of Zodia:** Standard Chartered's custodian is the UK bank with the deepest position in Hong Kong's new stablecoin licensing regime and the most institutional crypto reach across MENA. It is a jurisdictional tell: the first non-US regulated stablecoin on Tempo is more likely to come through the HK/Standard Chartered corridor than the euro corridor.

This is not cryptoeconomic security — it is governed financial market infrastructure. Closer to Visa or DTCC governance than Ethereum. The permissioned validator design functions as a compliance interface: bank risk committees can underwrite Visa, Zodia, and Stripe; they cannot easily underwrite anonymous cryptoeconomic validators.

Governance transparency: Henri Stern (Privy CEO, Stripe corporate family) publicly flagged the unresolved 2–3 year decentralization question in November 2025. This is on the record.

## Funding & traction

- **$5 billion Series A valuation** — led by Thrive Capital and Greenoaks; Paradigm and Stripe did not participate in the round
- **Mainnet launched:** March 18, 2026
- **TVL (mid-April 2026):** ~$3M — intentionally small; adoption curve is procurement-led and compliance-led, not DeFi-led
- **MPP transactions at mainnet launch:** ~50.7K (50+ days post-launch)

## Key people

- **Matt Huang** — CEO; also a Managing Partner at Paradigm ($12.7B crypto VC fund) and a Stripe board member. Triple role creates structural governance questions that are being monitored by institutional counterparties
- **Georgios Konstantopoulos** — Engineering Lead (formerly Paradigm's CTO)
- **Dan Romero** — Joined Feb 2026; co-founder of Farcaster
- **Varun Srinivasan** — Joined Feb 2026; co-founder of Farcaster
- **Dankrad Feist** — Joined Tempo team; formerly Ethereum Foundation researcher; publicly backed the mainnet launch
- **Liam Horne** — Former Optimism CEO, co-founded Connext during the 2018 state-channel era; built the one-way payment channel primitive at L1

**Farcaster founders signal:** The addition of Romero and Srinivasan suggests an agent identity layer is planned — Farcaster-style social graph primitives adapted for machine actors. This would be the identity layer that payments attach to.

## Products / offerings

- **Tempo L1** — EVM-compatible payment settlement chain
- **Tempo Zones** — Private EVM chains for enterprise; payroll, compliance, agent-scale microtransaction use cases
- **MPP settlement infrastructure** — co-authored with Stripe; Tempo is the stablecoin settlement rail for [[mpp]]
- **TIP-20** — Transfer-memo-aware stablecoin token standard with compliance controls

## Partner ecosystem

Design partners at mainnet launch: OpenAI, Anthropic, Deutsche Bank (testnet workloads), Mastercard, Nubank, Shopify, Klarna, Revolut, DoorDash, Fifth Third Bank, Coastal Community Bank, Visa, Standard Chartered (via Zodia), Fireblocks, Chainalysis.

Validator set expansion: Shopify announced joining at Sessions 2026 (April 29, 2026).

Note: Mastercard is simultaneously a design partner and the acquirer of BVNK ($1.8B direct Bridge competitor, March 2026). This tension may resolve in Mastercard exit from design partner list within 12 months.

## How Tempo relates to Ethereum

Tempo's Reth engineering improvements flow back upstream to Ethereum and the L2 ecosystem — the Tempo team has stated this explicitly. Tempo sits adjacent to Ethereum, not inside it: DeFi flows go to permissionless public chains; institutional B2B settlement, in the near term, is Tempo's target.

Dankrad Feist (former EF researcher now on Tempo): the gravity is real. Enterprise payments that move fast and don't require broad composability are Tempo's natural domain; DeFi composability and censorship resistance remain Ethereum's strengths.

## The Circle parallel

Tempo and [[circle-arc]] are architecturally convergent: permissioned L1 with named FI validators, stablecoin-native unit, sub-second finality, privacy primitives. Two companies independently arriving at the same design is evidence of a market category forming. The divergence is strategic platform: Circle goes institutional-first/policy-first; Tempo goes developer-distribution-first via Stripe's platform.

## Open questions

- Will Tempo's validator set decentralize on a credible timeline?
- When does an AI-agent-focused Tempo Zone launch (and who is the first operator — OpenAI or Anthropic)?
- Will Mastercard remain a design partner post-BVNK acquisition?
- What does an agent identity layer via Farcaster primitives actually look like?
- Can Tempo's adoption curve reach institutional procurement maturity before Ethereum L2s solve their congestion and compliance gaps?

## Sources

- [[what-are-stablecoins-tempo-1]]
- [[stripe-is-trying-to-make-crypto-disappear]]
- [[post-0xsammy-dripstack]]
