---
title: "What are stablecoins? — Tempo Docs"
type: summary
topic: agentic-money
source_type: company-blog
tags: [stablecoin, infrastructure, agentic-commerce, compliance, cross-border]
sources: ["What are stablecoins? ⋅ Tempo 1.md"]
created: 2026-04-25
updated: 2026-04-25
---

# What are stablecoins? — Tempo Docs

**Source:** [Tempo documentation](https://docs.tempo.xyz/learn/stablecoins) — last updated 2026-01-29
**Author:** Tempo (MPP co-author, stablecoin payments infrastructure)

## Key points

Tempo's explainer targets treasury and payments teams. It focuses exclusively on **fully reserved, fiat-backed stablecoins** (not algo or crypto-collateralized).

---

## How stablecoins work

- Issued by regulated entities, backed 1:1 with cash and short-term government securities
- **Mint-and-burn:** fiat in → stablecoins minted on-chain; stablecoins redeemed → burned, fiat returned
- Holders can always redeem at face value (in theory — counterparty risk applies)

## Why they matter for payments

- Near-instant settlement, 24/7, cross-border
- More predictable fees than legacy rails (ACH, wire, card)
- Enable programmable money: smart contracts auto-execute payments based on rules (e.g. auto-sweep subsidiary wallets based on balance thresholds)

## Use cases listed by Tempo

| Use case | Description |
|---|---|
| Remittances | Fast, cheap cross-border transfers |
| Global payouts | Instant payouts to contractors worldwide |
| Embedded finance | Payment flows embedded in platforms |
| Tokenized deposits | Real-time treasury liquidity movement |
| Microtransactions | Sub-cent payments for APIs, content, IoT |
| Agentic commerce | Autonomous agent payments for goods, services, digital resources |

## Key stats

- Circulating stablecoin supply: ~**$300 billion** today (grown 10x over 5 years)
- **US Treasury projection:** $3 trillion by 2030

## Regulatory landscape

- **EU:** MiCA — reserve mandates, issuer licensing
- **US:** GENIUS Act — federal framework for stablecoin issuance (still evolving)

## Tempo's stablecoin stack

- **TIP-20 token standard** — adds transfer memos, compliance controls, reward distribution to standard ERC-20 functionality
- Native stablecoin issuance and DEX for stablecoin-to-stablecoin swaps
- Purpose-built for stablecoin payments and issuance (and co-author of [[mpp]])

## Brief history

| Year | Event |
|---|---|
| 2014 | Tether (USDT) launched on Bitcoin via Omni Layer |
| 2017 | MakerDAO launches DAI — first decentralized, crypto-collateralized stablecoin |
| 2018 | Circle + Coinbase launch USDC, emphasizing regulatory compliance |
| 2020–21 | DeFi Summer: stablecoin market cap surges from <$10B to >$100B |

## Relevance to agentic money

Stablecoins are the de facto currency rail for agentic payments — x402, MPP, and AP2 all rely on them. This Tempo doc is notable because Tempo co-authored MPP and is building the stablecoin infrastructure that MPP runs on. Their framing of microtransactions and agentic commerce as first-class use cases signals where they see MPP headed.

## Related pages

- [[stablecoin]]
- [[tempo]]
- [[mpp]]
- [[x402]]
