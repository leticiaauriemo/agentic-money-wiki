---
title: "Agentic Payments ⋅ Tempo"
source: "https://docs.tempo.xyz/guide/machine-payments"
author:
published:
created: 2026-04-21
description: "Make agentic payments using the Machine Payments Protocol (MPP) on Tempo — charge for APIs, MCP tools, and digital content with TIP-20 stablecoins."
tags:
  - "clippings"
---
## Make Agentic Payments

Make agentic payments using the [Machine Payments Protocol](https://mpp.dev/) (MPP). MPP adds inline payments to any HTTP endpoint — agents, apps, or humans pay as part of their request, and the server verifies payment before returning the response.

## Try it out

See the full payment flow in action. The terminal creates an ephemeral wallet, funds it with testnet USDG, and makes a paid request to fetch a photo.

Press Enter or click to start

## Payment flow

A client requests a paid resource, the server responds with `402` and a `Challenge` describing the price. The client pays, retries with a `Credential` transaction, and the server returns the resource with a `Receipt`.

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 498.4 600" width="498.4" height="600" style="max-width: 100%; height: auto; display: block; margin: 0px auto; opacity: 1;"><defs><linearGradient id="grad-success" gradientUnits="userSpaceOnUse" x1="429.2" y1="0" x2="69.2" y2="0"><stop offset="0%" stop-color="#a1a1aa"></stop><stop offset="85%" stop-color="#16a34a"></stop></linearGradient></defs><line x1="69.2" y1="56" x2="69.2" y2="580" stroke="#d4d4d8" stroke-width="0.75" stroke-dasharray="6 4"></line><line x1="429.2" y1="56" x2="429.2" y2="580" stroke="#d4d4d8" stroke-width="0.75" stroke-dasharray="6 4"></line><rect x="20" y="20" width="98.4" height="36" rx="4" fill="#ffffff" stroke="#e4e4e7" stroke-width="1"></rect><text x="69.2" y="38" text-anchor="middle" dy="0.35em" font-size="14" font-weight="600" fill="#27272a">Client</text> <rect x="380" y="20" width="98.4" height="36" rx="4" fill="#ffffff" stroke="#e4e4e7" stroke-width="1"></rect><text x="429.2" y="38" text-anchor="middle" dy="0.35em" font-size="14" font-weight="600" fill="#27272a">Server</text></svg>
1. **Request** — Any HTTP method (`GET`, `POST`, etc.)
2. **Challenge** — `402` with `WWW-Authenticate: Payment` header describing amount, currency, and recipient
3. **Pay** — Client signs a transaction or fulfills payment off-chain
4. **Retry** — Client re-sends with `Authorization: Payment` header containing the Credential
5. **Deliver** — Server verifies, returns `200` with `Payment-Receipt` header

## Why Tempo

Tempo's transaction model is designed for agentic payments using MPP:

- **~500ms finality** — Deterministic confirmation fast enough for synchronous request/response flows
- **Sub-cent fees** — Low enough for micropayments and per-request billing
- **Fee sponsorship** — Servers can cover gas on behalf of clients so they only need stablecoins
- **2D and expiring nonces** — Parallel nonce lanes prevent payment transactions from blocking other account activity
- **High throughput** — Supports the on-chain settlement volume that payment channels generate at scale

## Payment intents

Two [intents](https://mpp.dev/protocol#payment-intents) are available on Tempo:

|  | **Charge** | **Session** |
| --- | --- | --- |
| **Pattern** | One-time payment per request | Continuous pay-as-you-go |
| **Latency** | ~500ms (on-chain confirmation) | Near-zero (off-chain vouchers) |
| **Best for** | Single API calls, content access, one-off purchases | LLM APIs, metered services, usage-based billing |
| **On-chain cost** | Per request | Amortized across many requests |

## Use cases

- **Paid APIs** — Charge per request without API keys, billing accounts, or signup flows.
- **MCP tools** — Monetize tool calls served through the Model Context Protocol. Agents pay per call without OAuth or account setup.
- **Digital content** — Charge per access for articles, data feeds, or media without subscription paywalls.

## Get started[Client quickstart](https://docs.tempo.xyz/guide/machine-payments/client)

[

Handle payment-gated resources automatically

](https://docs.tempo.xyz/guide/machine-payments/client)[

Agent quickstart

Discover services and make paid requests from a terminal or AI agent

](https://docs.tempo.xyz/guide/machine-payments/agent)[

Server quickstart

Add payment gating to your HTTP endpoints

](https://docs.tempo.xyz/guide/machine-payments/server)[

Accept one-time payments

Charge per request with on-chain settlement

](https://docs.tempo.xyz/guide/machine-payments/one-time-payments)[

Accept pay-as-you-go payments

Session-based billing with off-chain vouchers

](https://docs.tempo.xyz/guide/machine-payments/pay-as-you-go)

## SDKs and tools

| Tool | Package | Install |
| --- | --- | --- |
| CLI | `tempo request` | `curl -fsSL https://tempo.xyz/install \| bash` |
| TypeScript | `mppx` | `npm install mppx viem` |
| Python | `pympp` | `pip install pympp` |
| Rust | `mpp-rs` | `cargo add mpp` |

See the [full SDK documentation](https://mpp.dev/sdk) for API reference and advanced usage.

## Learn more

- [MPP documentation](https://mpp.dev/) — Full protocol docs, SDK reference, and guides
- [IETF specs](https://paymentauth.org/) — Normative protocol specification
- [Protocol overview](https://mpp.dev/protocol) — Challenges, Credentials, Receipts, and transports

Was this helpful?

[Suggest changes to this page](https://github.com/tempoxyz/docs/edit/main/src/pages/guide/machine-payments/index.mdx)

Last updated: 04/06/2026, 09:02 PM