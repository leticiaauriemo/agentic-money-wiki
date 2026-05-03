---
title: "x402 Whitepaper: Technical Specification"
type: summary
topic: agentic-money
source_type: report
tags: [infrastructure, agentic-commerce, crypto-l2]
sources: [x402-whitepaper.pdf]
created: 2026-04-26
updated: 2026-04-26
---

# x402 Whitepaper: Technical Specification

**Source:** x402 Whitepaper (PDF), Coinbase Developer Platform
**Authors:** Erik Reppel, Ronnie Caspers, Kevin Leffew, Danny Organ, Dan Kim, Nemil Dalal
**Published:** May 6, 2025

The primary technical specification document for the x402 protocol. Complements [[x402-whitepaper-summary]] (based on x402.org site) with implementation details, API schemas, and use case pricing.

## Abstract

x402 is an open payment standard that enables AI agents and web services to autonomously pay for API access, data, and digital services. One line of code: `paymentMiddleware(amount: "0.10", address: "0x...")`.

## Payment rail comparison (from whitepaper)

| Rail | Typical Fees | Settlement Finality | Chargeback Risk | Scalability |
|------|-------------|---------------------|----------------|-------------|
| Credit card | $0.30 + 2.9% | Days (batch) | Yes, up to 120 days | 65K TPS (theoretical) |
| PayPal | ~3% + markup | Instant auth, days to settle | Yes | Unknown |
| Stripe (Pay with Crypto) | 1.5%+ | Depends on chain | No | Depends on chain |
| Ethereum L1 | $1–$5 + gas | 1–2 min | No | 15–20 TPS |
| **x402 (on Base)** | **Free* (~$0.0001 gas)** | **~200ms** | **No** | **Hundreds–thousands TPS** |

## Four-step payment flow

1. **Client Request** — AI agent or app requests access to an API or digital resource
2. **Payment Required (402)** — Server responds with HTTP 402; provides pricing and payment details
3. **Agent Retries with Signed Payment** — Agent submits cryptographically signed payment authorization (EIP-712 standard)
4. **Web Service Verifies & Broadcasts** — Server validates, broadcasts to blockchain, returns resource

## Payment request JSON schema (402 response)

```json
{
  "maxAmountRequired": "0.10",
  "resource": "/api/market-data",
  "description": "Access to real-time market data requires payment.",
  "payTo": "0xABCDEF...",
  "asset": "0xA0b86991...",
  "network": "ethereum-mainnet"
}
```

Full payment request format fields:

| Field | Description |
|-------|-------------|
| `maxAmountRequired` | Maximum payment required (e.g., "0.10") |
| `assetType` | Token standard (e.g., "ERC20") |
| `assetAddress` | Contract address of the payment token |
| `paymentAddress` | Recipient wallet address |
| `network` | Blockchain network identifier |
| `expiresAt` | Timestamp after which request is no longer valid |
| `nonce` | Unique identifier to prevent replay attacks |
| `paymentId` | Unique identifier for this payment request |

## Settlement methods

x402 supports four settlement mechanisms:
1. **On-chain settlement** — direct blockchain transactions
2. **Layer-2 settlement** — optimistic or ZK rollups for lower fees
3. **Payment channels** — high-frequency micropayments between trusted parties
4. **Batched settlements** — combining multiple micropayments into one transaction

## Use case pricing examples (from whitepaper)

| Use Case | Price |
|----------|-------|
| Real-time stock market data (per request) | $0.02 |
| Computer vision image classification | $0.005 |
| Synthetic voice audio clip | $0.10 |
| GPU resources | $0.50/GPU-minute |
| Premium news article | $0.25 |
| Legal research court ruling | $0.10/document |
| Per-episode podcast | Pay-per-listen |
| Premium research journal whitepaper | Pay-per-download |

## Integration (one-liner middleware)

**Server (Node.js/Express):**
```javascript
app.get('/premium-data', x402PaymentRequired({
  amount: "0.10",
  address: "0x1234...",
  assetAddress: "0x2345...",  // USDC contract
  network: "base-mainnet"
}), handler);
```

**Client:**
```javascript
const client = new x402Client();
client.setWallet(wallet);
const data = await client.fetch('https://api.example.com/premium-data');
```

## Cryptographic signature

Payment authorizations use **EIP-712** standard — structured, typed data signing that enables clear presentation in wallet interfaces showing: request domain, payment amount, payment token, and specific resource being accessed.

## Key differentiators (per whitepaper)

- No chargebacks: push-only transactions with onchain finality
- No PCI compliance required for developers using a facilitator
- No API keys, accounts, or subscriptions
- Global access: permissionless, no FX conversion overhead
- Chain-agnostic: designed to support any stablecoin, digital asset, or blockchain

## Related pages

- [[x402]]
- [[x402-whitepaper-summary]]
- [[welcome-to-x402]]
- [[coinbase]]
