---
title: "The New Stack for Global Finance: Stablecoins Edition"
type: summary
topic: agentic-money
source_type: analysis
tags: [stablecoin, infrastructure, cross-border, bank-api, compliance, crypto-l1, crypto-l2]
sources: ["The new stack for global finance Stablecoins edition.md"]
created: 2026-04-28
updated: 2026-04-28
---

# The New Stack for Global Finance: Stablecoins Edition

**Source:** [a16z crypto](https://a16zcrypto.com/posts/article/global-finance-stablecoins-new-stack)
**Authors:** Noah Levine (investment partner), Guy Wuollet (general partner), Robert Hackett (features editor)
**Published:** 2026-04-27
**Context:** a16z crypto's market map of the stablecoin-powered global finance stack — covers the full infrastructure layer from blockchains through banking to credit markets.

## Core thesis

Stablecoins have evolved from a niche trading instrument into foundational plumbing for a new generation of global financial products. This is a new form of **banking-as-a-service**: not fintechs renting bank licenses plugged into legacy core systems (prior BaaS wave), but companies building on onchain infrastructure with self-custodial wallets, combining account, payment, FX, and credit primitives into end-to-end products.

Signal of structural shift: Stripe acquired Bridge + Privy; Mastercard acquired BVNK ($1.8B). Incumbents are buying the stack before the infrastructure layer settles.

## Three blockchain categories

The old assumption that all blockchains compete for the same use cases is breaking down:

**1. General-purpose chains** (Solana, Ethereum + major L2s) — primary home of crypto capital markets: trading, lending, DeFi. Durable market, but not the full picture.

**2. Payments-specific blockchains** — a new category competing on features general-purpose chains were never optimized for:
  - Stablecoin-native gas fees
  - Privacy guarantees
  - Predictable transaction costs (essential for fintechs modeling costs at scale)
  - Examples: [[tempo]] (Stripe's chain), **Circle's Arc** ([[circle-arc]])

**3. Institutional networks** — designed for regulated entities needing programmability + privacy without surrendering compliance frameworks:
  - Example: **Canton** ([[canton]])
  - As bank- and asset-manager adoption accelerates, this category becomes increasingly load-bearing

## Banking layer: the choke point is loosening

For a decade, banking partner relationships were existential risks for crypto-native companies. That dynamic hasn't disappeared but is meaningfully better. A cohort of crypto-friendly banks is actively building connectivity between crypto-native infrastructure and traditional fiat systems. The on-ramp/off-ramp problem is becoming tractable.

## Stablecoin issuers: OCC charter race

Post-GENIUS Act, a scramble among issuers to obtain an OCC National Trust Charter:
- Immediate benefit: legitimacy — a federal imprimatur that matters to regulators and institutional partners
- Longer-term stake: if OCC National Bank Charter holders get **direct access to Federal Reserve rails**, early charter holders become integrated into the core of the payment hierarchy
- The race is less about branding than about **where in the payment hierarchy you end up sitting** and who provides the foundation for credit and capital markets

## Liquidity providers: the last-mile problem

Cross-border "middle mile" is solved; the remaining problem is **last-mile liquidity** between stablecoins and local fiat, especially in emerging markets:
- **OpenFX, XFX** — stablecoin-compatible FX providers
- **Bitso** (Latin America), **Yellowcard** (Africa), **Coins.ph** (Southeast Asia) — regional exchanges with local fiat depth
- Banks that support stablecoin settlement for FX trades (still rare)

All three channels are necessary; no single one closes the gap alone.

## Bank connectivity: unglamorous critical layer

Stablecoin infrastructure was built almost entirely outside traditional banking — creating an architectural incompatibility with legacy core systems. The "bank connectivity" category builds the translation layer that lets banks offer stablecoin capabilities without a full system transplant.

## Applications layer: two dynamics

**1. Convergence between neobanks and crypto wallets** — exchanges adding virtual accounts, cards, rewards; neobanks integrating crypto. End state: unified financial app for crypto-native and mainstream users.

**2. Corporate banking in emerging markets** — where local dollar banking is limited, unreliable, or expensive (large parts of LatAm, sub-Saharan Africa, SE Asia), stablecoins enable dollar-denominated operations previously inaccessible: vendor payments, global collections, treasury management. The story is dollar access, not crypto.

**The wedge → full stack thesis:** Once a user (person or business) has a stable dollar balance, they have on-ramp to credit, investing, wealth management, and insurance — products they've never meaningfully had. Payments open the account; credit and investing build the business.

## Onchain credit market: act 2

Payments is act 1; credit is the more consequential act 2.

- Trillions in stablecoin float will create enormous demand for capital deployment
- Not self-referential DeFi (crypto lent against crypto to speculate on crypto) — something closer to productive credit: capital formation, lending against real assets and receivables, working capital for businesses in underserved markets
- Structural analogy: private credit over the last decade (banks retreated under regulatory pressure → private credit filled the gap → grew from niche to multi-trillion market). Onchain credit is structurally similar, but with open, programmable, global infrastructure underneath

See [[onchain-credit-market]].

## Dollar dominance and geopolitics

Every stablecoin wallet is a new node in the dollar-based financial system — settling value between any two points instantly at negligible cost. The GENIUS Act is not just regulation but a US geopolitical bet: stablecoin infrastructure as a vector for dollar primacy at a moment when that leadership faces challenges.

For end users: practical economic empowerment — protection from local currency devaluation, access to global rails, dollar operations without a US bank account.
For the US: amplification of dollar network effects, extending penetration into economies previously out of reach.

## Related pages

- [[stablecoin]]
- [[circle]]
- [[circle-arc]]
- [[canton]]
- [[tempo]]
- [[stripe]]
- [[bvnk]]
- [[mastercard]]
- [[onchain-credit-market]]
- [[9-charts-stablecoins-a16z]]
