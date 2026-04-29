---
title: "MPP (Machine Payments Protocol)"
type: rail
topic: agentic-money
tags: [infrastructure, stablecoin, agentic-commerce]
sources: []
created: 2026-04-25
updated: 2026-04-25
---

# MPP (Machine Payments Protocol)

**Type:** Machine-to-machine payment protocol
**One-line:** An open protocol co-authored by Stripe and Tempo enabling machines and AI agents to initiate, route, and settle payments autonomously.

## How it works

Details of the technical implementation are not yet fully public. MPP appears to define a standard communication layer for machine-initiated payments, distinct from x402's HTTP-embed approach. The protocol is tracked via the MPPscan explorer.

## Settlement speed & cost

Unknown — not yet detailed in public documentation.

## Who controls it

Co-authored by **Stripe** and **Tempo**. Governance model not yet public.

## Agent-friendliness

Designed specifically for machine-initiated payments. The MPPscan dashboard tracks agents and servers as first-class entities (6.5K agents, 452 servers registered as of 2026-04-25).

## Who is building on it

- Stripe — co-author, major payments infrastructure company
- [[tempo]] — co-author; purpose-built stablecoin infrastructure with TIP-20 standard, native stablecoin issuance and DEX

## Live stats (as of 2026-04-25)

| Metric | Value |
|---|---|
| Transactions (all time) | 50.7K |
| Volume (all time) | $7.27K |
| Agents | 6.5K |
| Servers | 452 |
| Avg. transaction size | ~$0.14 |

Dashboard offers 24h, 7d, 15d, 30d, and all-time filters with breakdowns by server, txns, volume, and agents.

Stats source: [MPPscan](https://mppscan.com/) (fetched 2026-04-25).

## Regulatory status

Unknown.

## Related concepts

- [[x402]] — competing protocol (Coinbase), 167M+ txns vs MPP's 50K
- [[ap2]] — Google's protocol; supports fiat and crypto, 60+ partners

## Open questions

- What rails does MPP settle on — stablecoin, fiat, or both?
- Why is transaction count so much lower than x402? Different use case, or later start?
- Is MPPscan the only explorer, or is there raw data / API access?
- What is Tempo's role — infrastructure provider or co-designer?
