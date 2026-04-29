---
title: "ERC-8004: Trustless Agents"
type: summary
topic: agentic-money
source_type: report
tags: [identity-kyc, infrastructure, compliance]
sources: ["ERC-8004 Trustless Agents.md"]
created: 2026-04-26
updated: 2026-04-26
---

# ERC-8004: Trustless Agents

**Source:** Ethereum Improvement Proposals, eips.ethereum.org/EIPS/eip-8004
**Status:** Draft — Standards Track (ERC)
**Created:** 2025-08-13
**Authors:** Marco De Rossi (MetaMask), Davide Crapis (Ethereum Foundation), Jordan Ellis (Google), Erik Reppel (Coinbase)
**Requires:** EIP-155, EIP-712, EIP-721, EIP-1271

The technical standard for discovering agents and establishing trust across organizational boundaries without pre-existing relationships — the [[know-your-agent]] layer on Ethereum.

## Abstract

Uses blockchains to **discover, choose, and interact with agents across organizational boundaries** without pre-existing trust — enabling open-ended agent economies. Trust models are pluggable and tiered, with security proportional to value at risk.

## Why it's needed

MCP handles tool/capability advertisement. A2A handles agent authentication and task orchestration. Neither covers **agent discovery and trust in untrusted settings**. ERC-8004 fills this gap for cross-organizational agent interactions.

## Three registries

### 1. Identity Registry
- Based on **ERC-721** (NFTs) with URIStorage extension — every agent gets an NFT, making agents immediately browsable and transferable via NFT tooling
- Global agent identifier: `{namespace}:{chainId}:{identityRegistry}` + ERC-721 tokenId
- Each token's URI points to an **agent registration file** containing:
  - Name, description, image
  - Service endpoints: A2A agent card, MCP endpoint, ENS name, DIDs, email, wallet addresses
  - `x402Support` flag
  - `supportedTrust` list (reputation, crypto-economic, tee-attestation)
- Agents can advertise on multiple chains; registered on one chain, transacting on others

### 2. Reputation Registry
- Any party can submit signed feedback (value + tags) on any registered agent
- On-chain storage for composability; off-chain (IPFS) for sophisticated aggregation
- Fields: `value` (int128 fixed-point), `tag1`/`tag2` (custom), `endpoint`, off-chain evidence URI
- Example tags: `starred` (0–100 quality), `reachable` (binary), `uptime` (%), `successRate`, `revenues`, `tradingYield`
- Feedback submitter cannot be the agent owner (prevents self-inflation)
- **x402 `proofOfPayment`** can be included in off-chain feedback files to enrich reputation signals
- Feedback is revocable; third parties can append responses (e.g., flagging spam)

### 3. Validation Registry
- Agents request independent verification of their work from validator smart contracts
- Validators can use: stake-secured re-execution, zkML proofs, TEE oracles
- `validationRequest()` → off-chain data URI + keccak256 commitment
- `validationResponse()` → 0–100 score (binary or spectrum), can be called multiple times for progressive finality
- Validator incentives/slashing managed by specific validation protocols (outside ERC-8004 scope)

## Trust model tiers

Pluggable trust proportional to value at risk:
- Low-stake: reputation systems (client feedback)
- Medium-stake: stake-secured re-execution
- High-stake: zkML proofs or TEE attestation

## Relationship to other protocols

| Protocol | Covers | Gap |
|----------|--------|-----|
| MCP | Capability advertisement | No cross-org trust |
| A2A | Auth, task orchestration | No discovery |
| **ERC-8004** | **Discovery + trust** | **Payments (defers to x402)** |

ERC-8004 explicitly notes payments are orthogonal and defers to x402 for that layer.

## Security considerations

- Sybil attacks possible — protocol makes signals public/schema-uniform; reputation systems around reviewers expected to emerge
- On-chain pointers/hashes cannot be deleted — permanent audit trail
- Cannot cryptographically guarantee advertised capabilities are functional or non-malicious — trust models address this

## Significance for agentic payments

ERC-8004 is the most technically mature proposal for the [[know-your-agent]] problem. Its four authors represent the key players across the agentic payments ecosystem (MetaMask/identity, Ethereum Foundation/protocol, Google/enterprise, Coinbase/x402). Cross-organizational commerce at scale requires this layer.

## Related pages

- [[know-your-agent]]
- [[x402]]
- [[ap2]]
- [[coinbase]]
- [[agentic-banking]]
