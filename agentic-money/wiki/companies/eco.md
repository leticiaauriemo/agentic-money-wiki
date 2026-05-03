---
title: "Eco"
type: company
topic: agentic-money
tags: [infrastructure, stablecoin, cross-border, agentic-commerce]
founded:
stage: private
hq:
sources: [Why AI Agents Need Stablecoin Payments.md]
created: 2026-05-03
updated: 2026-05-03
---

# Eco

**One-line:** A stablecoin execution network across 15 chains that abstracts routing, solver selection, and cross-chain liquidity for agent payments — positioning as the orchestration layer between payment protocols (x402, MPP) and underlying chains.

## What they're building

Eco is a cross-chain stablecoin routing and settlement network. When an agent needs to pay in USDC on Base but the merchant's treasury is on Solana, Arbitrum, or Tron, Eco handles the four routing decisions automatically:

1. Which chain settles the merchant fastest
2. Which liquidity source has depth at this size
3. Which bridge/transport moves the dollars
4. What finality guarantees apply on arrival

**Infrastructure:** Hyperlane as the live partner-rail for cross-chain messaging; CCTP (Circle's Cross-Chain Transfer Protocol) as the canonical-USDC transport. Spans 15 chains.

## Relevance to agentic money

As the number of agent payment surfaces grows (six major surfaces as of April 2026) and chain count increases (Visa's program is across 9 blockchains), the orchestration problem — getting the right dollars from the agent's chain to the merchant's chain — becomes load-bearing. Eco's pitch is that a developer should be able to use x402 or MPP for the request handshake, EIP-3009/Permit2 for the signature, and Eco for everything to do with where the money actually is and how it gets where it's going.

## Products / offerings

- **Stablecoin execution network** — cross-chain routing and settlement for payments and agent transactions
- Cross-chain liquidity via Hyperlane + CCTP
- 15-chain coverage as of April 2026

## Target developers

Developer-platform teams (agency tooling companies, startups) building on top of x402 or MPP who don't want to wire bridge logic themselves. The orchestration role is positioned between protocol layer and chain layer.

## Open questions

- What is Eco's business model — per-transaction fee, protocol fee, or spread on liquidity?
- What is Eco's funding and founding story?
- Which agents or merchants are using Eco in production today?
- How does Eco compete with or complement CCTP when routes are within CCTP's supported chains?

## Sources

- [[why-ai-agents-need-stablecoin-payments-eco]]
