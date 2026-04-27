---
title: "Agentic Payments — Tempo Docs"
type: summary
topic: agentic-money
source_type: company-blog
tags: [infrastructure, agentic-commerce, crypto-l2, payment-processor]
sources: [Agentic Payments ⋅ Tempo.md]
created: 2026-04-25
updated: 2026-04-25
---

# Agentic Payments — Tempo Docs

**Source:** [Tempo Docs](https://docs.tempo.xyz/guide/machine-payments)
**Last updated:** 2026-04-06

## What it explains

Tempo's technical documentation for Machine Payments Protocol (MPP) integration. Covers the HTTP 402 payment flow, two payment intents, SDK options, and use cases.

## HTTP 402 payment flow

1. Client requests paid resource
2. Server responds with `402 Challenge` describing price
3. Client pays and retries with `Authorization` header
4. Server verifies and returns `Receipt`

## Two payment intents

**Charge** (per-request)
- Use for: API calls, content access, one-time purchases
- Latency: ~500ms
- Model: each call initiates a new on-chain transaction

**Session** (continuous metered)
- Use for: LLM APIs, usage-based billing, high-frequency agent loops
- Latency: near-zero off-chain per call
- Model: authorize a session budget once, pay continuously within limit; settle periodically

## Performance characteristics

- ~500ms finality on Tempo
- Sub-cent fees for micropayments
- Supports 2D and expiring nonces (parallel nonce lanes so payment transactions don't block other activity)
- Fee sponsorship: servers can cover gas costs so clients only need stablecoins

## SDKs

- TypeScript: `mppx`
- Python: `pympp`
- Rust: `mpp-rs`
- CLI: `tempo request`

## Use cases

- **Paid APIs without API keys** — monetize endpoints directly via HTTP
- **MCP tool monetization** — charge per tool call in agent workflows
- **Per-access content paywall** — pay per read instead of subscribe

## Normative spec

Available at paymentauth.org (IETF-aligned standard).

## Relevance to agentic money

Session payments are the key MPP innovation over x402 for high-frequency use cases: one authorization, continuous execution. This is critical for agent loops that make dozens of calls per task.

## Related pages

- [[mpp]]
- [[tempo]]
- [[x402]]
- [[session-payments]]
