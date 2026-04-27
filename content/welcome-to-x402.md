---
title: "Welcome to x402 — Coinbase Developer Docs"
type: summary
topic: agentic-money
source_type: company-blog
tags: [infrastructure, agentic-commerce, crypto-l2]
sources: ["Welcome to x402.md"]
created: 2026-04-25
updated: 2026-04-25
---

# Welcome to x402 — Coinbase Developer Docs

**Source:** [Coinbase Developer Platform docs](https://docs.cdp.coinbase.com/x402/welcome)

## What it covers

Official developer documentation for the x402 protocol. Explains integration, SDKs, facilitator model, and discovery layer (Bazaar).

## Key technical details

- SDKs: TypeScript, Go, Python
- Supported tokens: ERC-20 payments on Base, Polygon, Arbitrum, World, Solana; EIP-3009 tokens (USDC, EURC) or Permit2 (any ERC-20)
- CDP facilitator: **1,000 free transactions/month**, then **$0.001/transaction**
- Two roles: server (resource provider) and client (agent or user paying)

## Facilitator model

The facilitator sits between payer and payee to handle the cryptographic handshake. CDP's facilitator is free to 1,000 txns/month, then $0.001/txn. Custom facilitators can be deployed. Planned roadmap includes KYC attestations and additional payment flows.

## Service discovery

**Bazaar** is x402's service discovery layer — a registry where servers list their endpoints and pricing so agents can discover and pay for services without prior coordination.

## Extensions

- **Gasless Permit2** — users don't pay gas, server sponsors it
- **Sign-in-with-x** — authentication alongside payment
- Facilitator extension system allows custom payment flows

## Relevance to agentic money

This is the canonical developer entry point for x402. The free tier (1,000 txns/month) lowers experimentation cost to zero; the Bazaar discovery layer is the embryo of a machine-readable service marketplace.

## Related pages

- [[x402]]
- [[coinbase]]
- [[marketplace-x402scan]]
