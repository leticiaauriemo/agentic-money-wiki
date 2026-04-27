---
title: "Know Your Agent (KYA)"
type: concept
topic: agentic-money
tags: [identity-kyc, compliance, infrastructure, agentic-commerce]
sources: [Should we give AI a bank account?.md, Is 2026 the Year of Agentic Payments?.md, Agentic Payments Use Cases Risks & How to Get Started.md]
created: 2026-04-25
updated: 2026-04-25
---

# Know Your Agent (KYA)

**One-line:** The agent-economy equivalent of KYC — verifying the identity, authorization, and behavioral bounds of an AI agent before allowing it to initiate financial transactions.

## How it works

KYA addresses three questions that KYC (Know Your Customer) does not:

1. **Identity** — Who or what is this agent? What model is it running? Who deployed it?
2. **Authorization** — What has the human principal explicitly authorized this agent to do? What spending limits apply?
3. **Behavioral bounds** — Is this agent operating within its authorized scope, or has it been compromised/hijacked?

Current approaches range from:
- **Platform-based authorization** — user grants agent access at onboarding; trust travels with session (PSD3 model)
- **Cryptographic mandates** — user signs Intent/Cart Mandates that encode exactly what agent can buy ([[ap2]] model)
- **Scoped credentials** — single-use tokens locked to specific transaction ([[visa]] Ramp Agent Cards, [[x402]] payment signatures)
- **On-chain identity** — ERC-8004 standard for persistent agent identity and reputation on blockchain
- **Licensed institution anchor** — in near term, agent identity maps back to a licensed financial institution (Sean Neville / [[catena-labs]] model)

## Why it matters for agentic money

KYA is identified as the most unresolved layer in agentic payments. Without it:
- Merchants can't verify an agent's authority to spend
- Banks can't comply with BSA/AML rules for non-human transactors
- Consumers can't prove an agent violated its authorization (for dispute resolution)
- Fraud models can't distinguish legitimate autonomous behavior from malicious bots

Sean Neville (Catena Labs) framed it as: "KYA is as critical as KYC." The agent identity verification and trust question is what his prior work at Circle (USDC) was to stablecoin payments — foundational infrastructure that must exist before the use cases scale.

## Current state

No universal KYA standard exists as of April 2026. Multiple approaches are being built simultaneously:
- [[ap2]] Mandates — closest to a verifiable credential standard
- [[mastercard]] Verifiable Intent (co-developed with Google) — tamper-resistant authorization records
- ERC-8004 — on-chain agent identity standard (emerging, used by ATXP, AgentLux in x402 ecosystem)
- NIST Center for AI Standards and Innovation — working on interoperable, secure AI agent identity standards
- MCP (Model Context Protocol) — provides a layer for agent context but not full identity

## Key players using / building this

- [[ap2]] — Mandate/VC model; most complete authorization framework
- [[mastercard]] — Verifiable Intent
- [[catena-labs]] — AI-native institution designed around agent identity
- ATXP — ERC-8004 on-chain agent identity (12.6K x402 transactions, largest server in ecosystem)
- AgentLux — agent identity and reputation engine, NFT-based on Base

## Related concepts

- [[bank-readiness-agentic-payments]] — fraud detection gap is a symptom of missing KYA
- [[stablecoin]] — agent needs wallet identity to hold and spend stablecoins
- [[agentic-commerce]]
- [[ap2]]

## Sources

- [[should-we-give-ai-a-bank-account]]
- [[is-2026-year-agentic-payments]]
- [[agentic-payments-use-cases-ramp]]
