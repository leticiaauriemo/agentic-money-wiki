---
title: "The Beginning of Agentic Finance"
type: summary
topic: agentic-money
source_type: analysis
tags: [infrastructure, crypto-l2, stablecoin, identity-kyc, agentic-commerce, compliance]
sources: ["The Beginning of Agentic Finance.md"]
created: 2026-04-28
updated: 2026-04-28
---

# The Beginning of Agentic Finance

**Source:** [Castle Labs Research](https://x.com/castle_labs/status/2047316059842388221)
**Authors:** @TradFiHater and @noveleader
**Published:** 2026-04-23
**Context:** Comprehensive thesis piece on Ethereum as the settlement layer for the agentic economy — 6 chapters, covering the tech stack, protocol competition, chain selection, and security challenges.

## Core argument

The agentic economy is not theoretical. Three converging EVM standards now form a complete financial system for machines:

- **[[x402]]** — payments (HTTP-native, Coinbase-built)
- **[[erc-8004]]** — trust and identity (onchain agent registry)
- **[[erc-8183]]** — commerce (escrow, work delivery, dispute resolution)

Together they cover the full commercial lifecycle: payment, identity, and verified work delivery. A fourth standard, **ERC-8211**, adds dynamic execution for multi-step DeFi strategies (April 2026).

## Structural problems x402 does not solve alone

Proof of personhood, architecture for humans (settlement cycles, banking hours, geographic routing), and gated access (prime brokerage, institutional custody) remain unsolved in traditional finance. The EVM stack above bypasses all three.

## x402 state in April 2026

- 50M+ transactions since May 2025 launch
- **V2 launched December 2025** with: wallet-based identity + reusable access sessions, modular architecture (spec / SDK / facilitator separation), Unified Payment Interface (multi-chain + legacy rails ACH/SEPA/card), and automatic API discovery
- **Upto scheme** (new): client authorizes a maximum amount; server settles for actual amount used — critical for LLM workloads where cost is unknown upfront
- Activity was >50% speculative (memecoins) until December 2025; has since stabilized at **~200K transactions/day** — the organic adoption floor
- Most volume flows through **Base** (not ETH L1), by design — micropayments need sub-cent gas

## ERC-8004 state in April 2026

- Live on mainnet since late January 2026
- **~98K agent registrations** across 10+ EVM chains
- Largest deployments: Base → Ethereum → MegaETH
- Three registries: Identity (ERC-721 onchain identity per agent), Reputation (verified interaction history), Validation (ZK/TEE third-party attestation — not yet live, under discussion)

## ERC-8183: the commerce layer

Co-developed by Virtuals.io protocol and the Ethereum Foundation dAI team. Defines a **Job primitive** — the onchain equivalent of the authorize-and-capture model:
- Client creates job, optionally locks funds in escrow
- Provider submits deliverable (hash pointing to IPFS/Arweave content)
- Evaluator (AI agent, ZK verifier, or multi-sig) accepts or rejects

Job states: Open → Funded → Submitted → Terminal (Completed / Rejected / Expired). Hooks enable bidding, reputation-gating, and privacy-preserving execution. Each completed Job feeds into ERC-8004 reputation registries — commerce activity compounds into trust.

**First working demo (early 2026):** OpenMind's OM1 robot dog paid for electricity autonomously — OM1 OS triggered spend, x402 handled HTTP payment negotiation, Circle Nanopayments batched offchain authorizations into single onchain settlements. No account, no credit card, no human.

## The competitive landscape

Three competing protocol visions:
- **Visa CLI** — agents trigger card payments from terminal, no API key management
- **Stripe + Tempo MPP** — privacy L1, ACP, Shared Payment Tokens; launch partners include both Visa and Mastercard (card networks backing the infrastructure competing with them)
- **x402 + ACP** — complementary: x402 for software-to-software (API calls, LLM interactions), ACP for e-commerce (fraud detection, dispute resolution, refunds)

**Galaxy Research travel agent example:** x402 pays for weather/airfare APIs; ACP handles flight booking (regulated, human-authorized); ERC-8183 provides escrow-and-evaluator for the gap between them.

**Citrini Research structural argument:** AI agents, programmed to minimize costs, will systematically avoid 2–3% interchange fees when stablecoin L2 transactions cost fractions of a cent.

## Why Ethereum specifically

Three arguments competitors can't easily replicate:
1. **Security** — ERC-8004 singleton contract lives on L1 (enterprise agents need that security anchor); 0 downtime since 2015
2. **Composability** — Aave, Uniswap, Chainlink, Morpho all in one atomic transaction
3. **Standards convergence** — x402, ERC-8004, ERC-8183, ERC-8211, A2A, MCP via Cloudflare all EVM-deployed; the Ethereum Foundation dAI team (led by Davide Crapis) exists with explicit mandate to make ETH the AI settlement layer

Solana is the only serious competitor; Tempo is EVM-compatible. Ethereum's estimated future: "within 3–5 years, the majority of Ethereum traffic will come from machines" (Crapis, dAI team).

## Security threats for agentic finance

1. **Public transaction transparency** — agent portfolio strategies are visible onchain
2. **RPC layer** — nodes see every query (contracts read, actions, IP address) before it becomes a transaction
3. **Network layer** — IP analysis and traffic-timing can deanonymize even encrypted content
4. **Wallet interface** — mouse patterns, device fingerprinting link users across fresh addresses
5. **Prompt injection** — poisoned ENS records, price feeds, or contract metadata instructing agents to send funds to attacker wallets; no phishing link required

Ethereum's response: **Kohaku** SDK (privacy-preserving transactions default), active in 2026 roadmap.

## CROPS mandate

Ethereum's framework for trustworthy agentic infrastructure — agents must be:
- **C**ensorship Resistant
- **O**pen-source
- **P**rivate (full-stack, not just at the agent layer)
- Provably **S**ecure (ZK proofs, formal verification)

## New players / entities mentioned

- **OpenMind** — built OM1 robot OS; first full-stack agentic commerce demo
- **ChaosChain** (Nethermind) — protocol for agentic accountability built on ERC-8004, A2A, x402
- **Davide Crapis** — lead of Ethereum Foundation dAI team
- **MegaETH** — third-largest ERC-8004 deployment chain

## Related pages

- [[x402]]
- [[erc-8183]]
- [[erc-8004-trustless-agents]]
- [[erc-8211]]
- [[crops-mandate]]
- [[coinbase]]
- [[acp]]
- [[mpp]]
- [[stablecoin]]
- [[x402-governance]]
