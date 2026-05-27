---
title: "An Overview of EIP-3009: Transfer With Authorization"
type: summary
topic: agentic-money
source_type: analysis
tags: [stablecoin, infrastructure, crypto-l2, x402]
sources: ["An Overview of EIP-3009 Transfer With Authorisation.md"]
created: 2026-05-27
updated: 2026-05-27
---

# An Overview of EIP-3009: Transfer With Authorization

**Source:** Extropy Academy (Laurence Kirk)
**URL:** https://academy.extropy.io/pages/articles/review-eip-3009.html

## What it is

EIP-3009 is an ERC-20 extension titled "Transfer With Authorization." It introduces **meta-transactions** for stablecoin transfers, allowing the token holder to sign an off-chain authorization that any third-party "relayer" can submit on-chain. The relayer pays the gas.

USDC V2 (Circle) implements EIP-3009. It is the signature substrate that makes x402 gasless agent payments possible.

## The problem it solves

Before EIP-3009, paying with an ERC-20 token required **two on-chain transactions** (and two gas fees):
1. `approve` — authorize a contract to spend tokens
2. `transferFrom` — execute the actual transfer

This created two critical problems:
- Bad UX (two wallet pop-ups, two fees)
- **The gas token problem** — the user must hold ETH to pay gas even when only spending USDC. This is a non-starter for AI agents that cannot manage multiple wallet balances.

## How it works

1. **Off-chain signing:** The agent creates a structured EIP-712 message containing: `from`, `to`, `value`, `validAfter`, `validBefore`, and a random `bytes32` nonce. Signs with private key.
2. **Relayer submission:** Client sends the signed authorization to a relayer (e.g., x402 facilitator), which pays gas and calls `transferWithAuthorization(...)` on the token contract.
3. **On-chain verification:** Contract uses `ecrecover` to verify signature, checks nonce hasn't been used, confirms timestamp window, then executes the transfer.

## Key technical features for agent payments

- **Atomic transfer:** Unlike EIP-2612 (`permit`), which only authorizes an approval, EIP-3009 authorizes the **entire transfer** in a single call
- **Non-sequential nonces:** Uses random `bytes32` hash nonces (not sequential integers), allowing **thousands of concurrent payment authorizations** without ordering bottlenecks — critical for high-frequency agent workloads

## The fragmentation problem

EIP-3009 is not universal:
- **USDC V2** — implements EIP-3009 (`transferWithAuthorization`)
- **DAI** — implements EIP-2612 (`permit`) — similar but incompatible
- **USDT (Tether)** — implements **neither** and has no plans to

This "token exclusivity" limits purely EIP-3009-based protocols (like x402's native path) to USDC, excluding the largest stablecoin by market cap.

## Relevance to this wiki

EIP-3009 is the cryptographic primitive underlying x402 and the MPP signature standard. When an agent "pays" via x402, it is signing an EIP-3009 authorization. Understanding EIP-3009 explains why x402 is USDC-first, gasless, and capable of concurrent micropayments.

## Related pages

- [[x402]] — x402 protocol uses EIP-3009 for its payment signature
- [[x402-whitepaper-technical]] — x402 technical specification
- [[mpp]] — Machine Payments Protocol (also uses EIP-3009 / Permit2 substrate)
- [[stablecoin]] — USDC vs. USDT landscape
- [[session-payments]] — how non-sequential nonces enable session models
