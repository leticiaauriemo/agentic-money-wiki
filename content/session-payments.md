---
title: "Session Payments"
type: concept
topic: agentic-money
tags: [infrastructure, agentic-commerce, payment-processor]
sources: ["Agentic Payments ⋅ Tempo.md", "Post by @0xCygaar on X.md", "Introducing the Machine Payments Protocol.md"]
created: 2026-04-26
updated: 2026-04-26
---

# Session Payments

**One-line:** A payment model where a user or agent authorizes a budget once, then executes many micropayments within that authorization without re-approval per call — critical for high-frequency agentic workflows.

## How it works

1. User/agent authorizes a session with a defined budget (e.g., $5 session limit)
2. Agent executes many API calls or resource requests within the session
3. Each call draws down the session budget at near-zero latency (off-chain)
4. At session end (or budget exhaustion), a single settlement transaction occurs on-chain

Contrasted with **per-call payments** (x402 model): each API call requires its own on-chain transaction (~200–500ms latency, transaction fee per call).

## Why it matters for agents

Agent loops commonly make dozens to hundreds of sub-calls per task:
- An AI coding agent may call 50 tool endpoints while completing one feature
- A research agent may query 20 data sources in a single workflow
- A trading agent may check market conditions hundreds of times before executing

Per-call payment overhead (even at $0.0001 per call) accumulates, and the latency (~200–500ms per call) becomes a bottleneck. Session payments eliminate both: one authorization, continuous execution.

## Who implements it

**[[mpp]] (Machine Payments Protocol)** — Session is one of two native payment intents:
- **Charge** — per-request, ~500ms latency, on-chain per call
- **Session** — authorize once, near-zero off-chain latency per call, settle periodically

**[[tempo]]** implements Session via 2D nonces and expiring nonce lanes that prevent payment transactions from blocking other activity.

## Comparison with x402

| Dimension | x402 | Session (MPP) |
|-----------|------|----------------|
| Per-call overhead | On-chain transaction (~200ms) | Near-zero (off-chain) |
| Authorization | Per-call | Once per session |
| Settlement | Per-call | Periodic batch |
| Best for | Occasional, high-value calls | High-frequency agent loops |

## Current state

Live on Tempo Mainnet (launched March 18, 2026). MPP Session is the specification; Tempo is the reference implementation.

## Related concepts

- [[mpp]]
- [[x402]]
- [[tempo]]
- [[agentic-commerce]]
