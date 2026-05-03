---
title: "x402 Whitepaper"
type: summary
topic: agentic-money
source_type: report
tags: [infrastructure, stablecoin, crypto-l2, agentic-commerce]
sources: [x402-whitepaper.pdf]
created: 2026-04-25
updated: 2026-04-25
---

# x402 Whitepaper

**Source:** Coinbase Developer Platform, May 6, 2025
**Authors:** Erik Reppel, Ronnie Caspers, Kevin Leffew, Danny Organ, Dan Kim, Nemil Dalal

## Core thesis

Legacy payment systems (ACH, credit cards, Stripe) are designed for humans and fail AI agents on every dimension: require account creation, manual setup, high fees ($0.30 + 2.9% per card transaction), slow settlement (1–3 days for ACH, days for card finality), chargeback risk, and no micropayment support.

x402 fixes this with one line of code: `paymentMiddleware(amount: "0.10", address: "0x...")`.

## Technical spec

**Payment flow (4 steps):**
1. Client requests API resource
2. Server responds HTTP 402 with JSON payload: amount, asset address, network, wallet address, expiry, nonce
3. Client signs payment authorization (EIP-712 standard) and retries request with signature
4. Server verifies signature, broadcasts on-chain, returns resource

**Performance vs. alternatives (from whitepaper table):**

| Rail | Fees | Settlement | Chargeback | Scalability |
|---|---|---|---|---|
| Credit Card | $0.30 + 2.9% | Days (batch) | Yes, up to 120d | 65K TPS (theoretical) |
| PayPal | ~3% + markup | Days settlement | Yes | Unknown |
| Ethereum L1 | $1–$5 gas | 1–2 min | No | 15–20 TPS |
| x402 (Base) | ~$0.0001 gas | **200ms** | No | Hundreds–thousands TPS |

**Settlement options:** On-chain direct, Layer-2 rollup, payment channels (high-frequency), batched settlements.

**Chain/token agnostic:** Designed to support any stablecoin or blockchain; USDC/Base is reference implementation.

## Key business model insights

**Micropayments unlocked:** Card rails make sub-cent payments uneconomical ($0.30 floor per transaction). x402 on Base costs ~$0.0001 per transaction — enabling true pay-per-request at fractions of a cent.

**Eliminated overhead:** No PCI compliance for developers, no chargebacks, no fraud reserves, no API key management, no rolling 120-day settlement windows.

**New business models enabled:**
- Pay-per-article at $0.25 (vs. monthly subscription)
- Trading AI paying $0.02 per stock data request
- Computer vision API at $0.005 per image classification
- GPU compute at $0.50 per GPU-minute

## Relevance to agentic money

This is the foundational technical document for x402 — the "why it exists" and "how it works" at the protocol level. Published May 2025 before the ecosystem grew to 167.96M transactions. The whitepaper's framing of "1.4 billion unbanked people" suggests x402's permissionless model also has financial inclusion implications beyond AI agents.

## Related pages

- [[x402]]
- [[coinbase]]
- [[stablecoin]]
