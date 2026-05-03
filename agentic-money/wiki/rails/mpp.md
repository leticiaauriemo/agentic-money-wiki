---
title: "MPP (Machine Payments Protocol)"
type: rail
topic: agentic-money
tags: [infrastructure, stablecoin, agentic-commerce]
sources: [Introducing the Machine Payments Protocol.md, Stripe Is Trying to Make Crypto Disappear.md, Post by @0xSammy on X.md]
created: 2026-04-25
updated: 2026-05-03
---

# MPP (Machine Payments Protocol)

**Type:** Machine-to-machine payment protocol (submitted to IETF)
**One-line:** Stripe and Tempo's open standard for AI agent payments over HTTP — rail-agnostic at launch, with four production features over x402, a pre-funded session model enabling off-chain micropayments, and a Visa card extension. Submitted to the IETF as a proposed payment authentication scheme.

## How it works

MPP shares [[x402]]'s HTTP 402 handshake pattern but adds four production features:

| Feature | What it adds |
|---------|-------------|
| First-class idempotency | Safe retries without double-charges |
| Request-body digest binding | Payment credential is cryptographically bound to the specific request content |
| Credential expiration | Prevents replayed or stolen credentials |
| Structured receipts | Machine-readable proof of payment for audit and reconciliation |

**Two payment intents:**
- **Charge** — per-call payment (~500ms settlement); agent pays once per resource access
- **Session** — authorize once, spend continuously against balance via off-chain vouchers settled in batches; sub-second latency for individual payments within session

**Session model mechanics:** An agent deposits funds once (the "pre-funded session"). Subsequent payments are off-chain voucher claims against that balance, settled in batches to Tempo mainnet. This is Lightning for stablecoins — enabled by Tempo's one-way payment channel primitive at L1, built by Liam Horne (former Optimism CEO) on the Tempo team. Makes token-streaming and per-inference billing economically viable.

## Rail support (multi-rail at launch)

| Rail | How |
|------|-----|
| Stablecoin (USDC) | Settled on [[tempo]] mainnet |
| Fiat (cards, BNPL) | Via Shared Payment Tokens (SPTs) — user-issued credentials passable to agents |
| Bitcoin Lightning | Via [[lightspark]] integration |
| Visa card extension | MPP extension published by Visa's engineering team (six-month in-house build) |

This rail-agnosticism is strategic. When an agent pays via MPP using an SPT (card-backed), interchange is preserved and Stripe stays in the flow. When the agent pays via MPP using stablecoin, settlement happens on Tempo — also touching Stripe's balance sheet. Either way, Stripe is not disintermediated.

## Relationship to x402

MPP and x402 share the same HTTP 402 handshake base. They are more parallel than competing at the protocol layer:
- x402 began as HTTP stablecoin-native; x402 Foundation is generalizing it
- MPP added production features for enterprise use (idempotency, receipt, session model)
- x402 Foundation participants include Adyen, AWS, American Express, Google, Mastercard, Shopify, Stripe, and Visa
- The two may converge at the foundation layer within 12 months

Stripe's actual stance: embrace and absorb. Stripe's own documentation supports both protocols. The goal is not to win the protocol war — it is to ensure the winning protocol terminates inside Stripe's balance, compliance, and reporting layer.

For users: MPP's first-party marking (each service card explicitly labeled as official integration) is a governance advantage over [[x402-governance]] where unauthorized wrapper operators are indistinguishable from first-party APIs.

## Who controls it

Co-authored by **[[stripe]]** and **[[tempo]]**. Submitted to IETF as a proposed payment authentication scheme. The x402 Foundation (Linux Foundation entity) includes Stripe as a participant — suggesting Stripe sees convergence as a viable path.

## Settlement speed & cost

- **Charge intent:** ~500ms end-to-end
- **Session intent:** Sub-second per individual payment (off-chain vouchers batched to L1)
- **Cost:** Sub-cent for stablecoin route on Tempo; card route preserves existing interchange structure

## Agent-friendliness

Designed specifically for machine-to-machine payments. First-class primitives:
- Sessions for high-frequency loops
- Per-call charges for discrete resource access
- Scoped credentials (SPTs) for consumer-delegated payments
- Visa card extension for card-based agent workflows

## Who is building on it

- [[stripe]] — co-author; Agentic Commerce Suite; merchant distribution
- [[tempo]] — co-author; settlement chain; Tempo Zones
- [[visa]] — card extension; anchor Tempo validator; Trusted Agent Protocol integration
- [[lightspark]] — Bitcoin Lightning rail
- [[merit-systems]] — MPPscan explorer
- DripStack (Michael Blau) — live demo: $0.01/article Substack payments via MPP on Tempo and x402 on Base
- Browserbase — paying per headless browser session via MPP
- PostalForm — monetizing physical mail services via MPP

## Live stats (as of April 2026)

| Metric | Value |
|--------|-------|
| Transactions (all time, ~45 days since mainnet) | 50.7K |
| Volume (all time) | $7.27K |
| Agents registered | 6.5K |
| Servers | 452 |
| Avg. transaction size | ~$0.14 |

Stats source: [MPPscan](https://mppscan.com/) (fetched 2026-04-25). Volume is lower than [[x402]] (167M txns) because MPP launched in March 2026 vs. x402 in May 2025, and because MPP's primary adoption curve is enterprise/procurement-led rather than permissionless-developer-led.

## Regulatory status

Submitted to the IETF as a proposed payment authentication scheme. No regulatory issues identified.

## Related concepts

- [[x402]] — parallel protocol; shares HTTP 402 base; may converge
- [[ap2]] — Google's mandate/authorization layer (different layer of the stack)
- [[session-payments]] — the authorize-once micropayment model
- [[tempo]] — the settlement chain for stablecoin MPP payments
- [[lightspark]] — Bitcoin Lightning integration
