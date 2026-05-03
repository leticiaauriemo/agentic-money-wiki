---
title: "How Agentic AI Will Reshape Payments — IMF Note 2026/004"
type: summary
topic: agentic-money
source_type: report
tags: [infrastructure, compliance, agentic-commerce, identity-kyc, stablecoin, bank-api]
sources: [2957-4390-068.2026.issue-004-en.pdf]
created: 2026-04-26
updated: 2026-04-26
---

# How Agentic AI Will Reshape Payments — IMF Note 2026/004

**Source:** International Monetary Fund, IMF Note 2026/004
**Authors:** Sonja Davidovic and Hervé Tourpe
**Published:** April 2026
**Pages:** 26

This is the IMF's official analysis of agentic AI in payment systems — the first major multilateral institution paper on the topic.

## Core argument

The central challenge is the **collision of two design logics**: payment systems are built on deterministic infrastructure (predictable, auditable, legally final). Agentic AI relies on probabilistic reasoning and adaptive decision making. These must be carefully reconciled, not merged.

The IMF does not propose prescriptive policy measures. It frames key design questions, architectural tensions, and risk channels for policymakers as adoption evolves.

## The three-layer framework (IMF's model)

The IMF proposes separating agentic payment functions into three layers:

### Layer 1 — Intent and Orchestration
Probabilistic AI systems that translate user objectives into structured instructions. No authorization or execution happens here.

**Technologies:** LLMs, MCP (contextual tool access), A2A (agent coordination), x402 (embedded payment negotiation in HTTP), Universal Commerce Protocol (UCP — Google, Jan 2026)

### Layer 2 — Control and Authorization
Deterministic rules that govern whether Layer 1 proposals may proceed. Only verified, scope-limited instructions pass through.

**Technologies:** AP2 (cryptographic mandates), OAuth 2.0 / OpenID Connect (KYA verification), ERC-8004 (on-chain agent identity/reputation), ERC-1812 (off-chain verifiable claims), ERC-6900 (modular smart accounts with spend limits and velocity controls), AML/KYC filters, card network rules

### Layer 3 — Settlement
Traditional deterministic settlement infrastructure. Takes only instructions that passed Layer 2; executes without modification.

**Technologies:** RTGS systems, card network clearing engines, CBDC platforms, DLT-based settlement rails, ERC-4337 (smart contract wallet execution)

**Key principle:** Innovation concentrates upstream (Layers 1–2). Settlement (Layer 3) should remain non-probabilistic to preserve legal certainty and systemic stability.

## New companies and protocols mentioned

**Google Universal Commerce Protocol (UCP)** — launched January 2026; standardizes discovery → comparison → offer → checkout for agents; enables "Native Checkout" within Google Search AI Mode and Gemini (users buy from Etsy, Wayfair without leaving the AI surface).

**Amazon "Buy for Me"** — Rufus assistant navigates external websites and completes transactions on behalf of customers; positions the shopping agent as primary interaction surface.

**OpenAI "Instant Checkout"** in ChatGPT — powered by Agentic Commerce Protocol (with Stripe); charges a **4% transaction fee** for autonomous agent-led conversions (confirmed new data point).

**PayPal acquisition of Cymbio (2026)** — positions PayPal as the "trust layer" for the agentic web; uses PayPal transaction graph and secure vaults for settlement while merchants maintain merchant-of-record status.

**Citi + Ant International** — AI-powered tool aimed at reducing FX hedging costs (live pilot).

## Risk classification matrix (10 risk categories)

| Risk | Primary source | Who bears cost | Policy intervention needed? |
|------|---------------|---------------|----------------------------|
| Instruction gap (structural vs. transactional authorization) | Account holders delegating broad mandates | Account holders, PSPs, payment systems | Yes — legal authorization model mismatch |
| Opacity of agent decision making | AI developers/deployers | Users, PSPs, supervisors | Yes — information asymmetry |
| High-speed machine-time execution | Agents optimizing speed | PSPs, end users (error propagation) | Yes — coordination externalities |
| Authorization traceability failures | PSPs relying on mandates without auditability | PSPs, users, courts | Yes — legal uncertainty |
| Ambiguous liability allocation | Outdated liability assumptions | PSPs, users | Yes — incomplete responsibility allocation |
| Product liability from autonomous behavior | AI developers, platforms | PSPs, platforms, users | Yes — product liability not designed for adaptive systems |
| Correlated agent behavior (herding) | Homogeneous models, shared optimization | Payment systems, PSPs | Yes — coordination externalities, systemic risk |
| Intraday liquidity stress | Agents optimizing payment timing | Payment systems, central banks | Yes — systemic liquidity externalities |
| Cybersecurity attack surface | Platforms integrating agents with APIs | Users, PSPs, payment systems | Yes — security externalities |
| DLT settlement without legal finality | System designers | Users, intermediaries | Yes — legal infrastructure gap |

## Key stats and projections

- **Gartner (2025):** AI agents will autonomously resolve **80% of customer service issues** without human intervention by 2029
- **BIS (2025):** Generative AI systems can fulfill cash management functions (liquidity buffers, payment prioritization, settlement trade-offs) without specialized training
- **OpenAI/Stripe:** 4% transaction fee on agent-led autonomous conversions via Agentic Commerce Protocol

## Mitigation strategies

**Systemic:**
- Human-in-the-loop required for high-value/high-risk transactions (with threshold-based triggers)
- "Kill switches" — distributed (not centralized), graduated (not binary), with clear authority and auditability
- Architectural separation: agents propose → deterministic execution layer verifies and executes

**Private sector:**
- Payment networks: launch agent-ready card products; build global agent registries with identity verification and reputation scoring; introduce dispute resolution frameworks for AI-initiated transactions
- Digital wallet providers: deploy passkey/biometric authentication that works in conversational interfaces; preserve merchant-of-record even for agent-initiated transactions
- Strong cybersecurity: scoped authorization, secure API governance, containment of cross-system privilege escalation

**Public sector:**
- KYC → KYA shift: mandate verifiable identities for financial bots linked to legal entities
- Real-time monitoring systems for anomalous agent behavior
- Regulatory sandboxes for testing agentic payment systems before full deployment
- Singapore's model governance framework cited as leading example
- EU AI Act applies to agentic AI applications

## Why this matters

This is the first IMF note on agentic payments. The IMF's endorsement of the three-layer framework (intent → authorization → settlement) provides institutional legitimacy to an architectural principle that industry players (AP2, Visa, Mastercard) are already building toward. The risk matrix also provides the clearest policy-level articulation of what could go wrong — from herding/flash crashes to the EFTA liability gap.

## Related pages

- [[ap2]]
- [[know-your-agent]]
- [[bank-readiness-agentic-payments]]
- [[agentic-ai-payments-regulatory-frameworks]]
- [[stablecoin]]
- [[x402]]
- [[mastercard]]
- [[visa]]
