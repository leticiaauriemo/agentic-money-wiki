---
title: "Stablecoin"
type: concept
topic: agentic-money
tags: [stablecoin, infrastructure, cross-border, agentic-commerce, compliance]
sources: ["What are stablecoins? ⋅ Tempo 1.md"]
created: 2026-04-25
updated: 2026-04-25
---

# Stablecoin

**One-line:** A blockchain-based digital asset pegged to a stable value (usually 1 USD) via reserves, enabling programmable, 24/7, cross-border payments without cryptocurrency volatility.

## How it works

Fully reserved fiat-backed stablecoins (the dominant type for payments) operate via **mint-and-burn**:
1. User deposits fiat with a regulated issuer
2. Issuer mints equivalent stablecoins on-chain and sends to user
3. On redemption, issuer burns tokens and returns fiat from reserves

Reserves typically held in cash and short-term government securities at licensed financial institutions. Major issuers publish reserve attestations (frequency and detail vary).

## Why it matters for agentic money

Stablecoins solve two critical problems for agent-initiated payments:
1. **Micropayment economics** — sub-cent transactions are viable on-chain in a way that card rails (1–3% fees) make impossible
2. **Programmability** — smart contracts can trigger payments automatically based on rules, with no human approval required at transaction time

This is why [[x402]], [[mpp]], and [[ap2]] all route through stablecoins rather than traditional fiat rails.

## Current state

- Circulating supply: ~**$300 billion** (grown 10x over 5 years) — *source: [[what-are-stablecoins-tempo-1]]*
- US Treasury projects $3 trillion by 2030
- Stablecoin transaction volume reached $33 trillion in 2025, up 72% YoY — *source: web search, unverified against primary source*
- Dominant assets: USDC (Circle/Coinbase, compliance-focused), USDT (Tether, largest by market cap)

## Key regulatory frameworks

| Jurisdiction | Framework | Status |
|---|---|---|
| EU | MiCA | In force — reserve mandates, issuer licensing |
| US | GENIUS Act | Proposed federal stablecoin framework, evolving |

## Key players using / building this

- [[coinbase]] — issues USDC (with Circle), uses USDC as x402's primary rail
- [[tempo]] — purpose-built stablecoin payments infrastructure, MPP co-author; TIP-20 standard
- Circle — USDC issuer
- Tether — USDT issuer (largest stablecoin by market cap)

## Related concepts

- [[programmable-money]]
- [[x402]]
- [[mpp]]
- [[ap2]]

## Sources

- [[what-are-stablecoins-tempo-1]]
