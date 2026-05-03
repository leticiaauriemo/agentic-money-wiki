---
title: "Bridge"
type: company
topic: agentic-money
tags: [stablecoin, infrastructure, compliance, payment-processor]
founded: 2022
stage: acquired
hq: San Francisco, CA
sources: [Stripe Is Trying to Make Crypto Disappear.md]
created: 2026-05-03
updated: 2026-05-03
---

# Bridge

**One-line:** Stripe's stablecoin orchestration and issuance subsidiary — operating Open Issuance (the "app store" for branded stablecoins) and pursuing an OCC national trust bank charter to become the custody bank for third-party stablecoin issuers.

## What they're building

Bridge provides the orchestration and issuance layer inside Stripe's stablecoin stack. Two products:

**1. Stablecoin orchestration** — cross-chain routing, compliance, and reserve management for enterprises managing stablecoin flows.

**2. Open Issuance platform** (launched September 2025) — a turnkey platform for issuing branded stablecoins. Phantom, Klarna, Hyperliquid, and MetaMask have all issued their own stablecoins on Bridge. Economics: issuers keep the **majority of reserve yield** (Bridge takes a take rate on the float). This turns reserve income into app-store economics — Stripe doesn't need to own every branded coin; it owns the platform where coins are launched, custodied, swapped, reconciled, and regulated.

**3. xUSD** — Bridge's own stablecoin; primary asset of Bridge National Trust Bank.

## Relevance to agentic money

Bridge is the issuance layer in Stripe's full agentic payment stack. When Meta sends stablecoin payouts to creators in the Philippines or Colombia, or when Klarna issues USD to customers, the stablecoin launches, settles, and complies via Bridge. Every stablecoin-native payment that terminates inside Stripe's ecosystem touches Bridge's reserve and compliance infrastructure.

## Funding & traction

- Founded: 2022
- Acquired by Stripe: October 2024, **$1.1 billion** (largest crypto M&A on record at the time; since surpassed by Mastercard's BVNK acquisition at $1.8B, March 2026)
- First-year payment volume on a steeper exponential than Stripe's own first two years of existence
- Open Issuance partners: Phantom, Klarna, Hyperliquid, MetaMask (as of May 2026)

## Key people

- **Zach Abrams** — co-founder, CEO; previously CPO at Brex, engineer at Coinbase
- **Sean Yu** — co-founder
- **Michael Lempres** — named organizer of Bridge National Trust Bank; formerly Coinbase's Chief Legal and Risk Officer; before that, Asst. Secretary of Defense and Chief of Staff at Treasury

## OCC National Trust Charter (Bridge National Trust Bank)

OCC conditional approval: **February 2026**. Conditions: $45M Tier 1 capital; eligible liquid assets equal to the greater of 50% of Tier 1 capital or $27.5M for the first three years; capital raised within 12 months; bank open within 18 months; charter limited to trust activities.

**What Bridge will do once open:** issue stablecoins, serve as primary issuer of xUSD, provide custody for affiliates and unaffiliated institutional customers.

**Key detail:** The charter is not to hold Stripe's own reserves. It is to be the bank that other people custody through. The capacity to custody third-party stablecoin reserves at scale is the strategic endgame.

**Analyst prediction ([@snapcrackle](https://x.com/snapcrackle/status/2050910293597856077)):** Within 18 months of final approval, Bridge applies for expanded OCC authorities to custody stablecoin reserves for third-party fintechs.

**Structural note:** A national trust charter does not make Stripe a bank holding company under the Bank Holding Company Act — Stripe gets federal regulatory legitimacy without becoming bank-regulated.

## GENIUS Act regulatory positioning

The OCC's proposed rule (March 2026) explicitly protects the non-affiliate yield-sharing that powers Open Issuance economics. Bridge sharing reserve yield with Klarna (a non-affiliated licensed Swedish bank) remains allowed. Consumer-facing yield programs through affiliated intermediaries (closer to the Coinbase USDC rewards model) are targeted. Bridge's B2B stablecoin infrastructure is GENIUS-aligned by construction.

## Partnership with Stripe

Bridge sits inside Stripe's orbit with compounding distribution advantages no standalone stablecoin orchestrator has. The same distribution that gave Bridge a steeper first-year ramp than Stripe itself benefits Privy, Tempo, and the trust charter once plumbed into Stripe's platform.

## Related pages

- [[stripe]] — parent company
- [[tempo]] — settlement layer for Bridge-issued stablecoins
- [[mpp]] — the protocol layer above Bridge's payment infrastructure
- [[stablecoin]] — the asset class
- [[the-new-stack-for-global-finance-stablecoins]] — positions Bridge in the broader OCC charter race context
- [[stripe-is-trying-to-make-crypto-disappear]] — the source for most detail on this page
