---
title: "The Agentic Protocol Stack (KYAPay Framework)"
type: summary
topic: agentic-money
source_type: analysis
tags: [identity-kyc, infrastructure, agentic-commerce, compliance]
sources: [The Agentic Protocol Stack.md, KYA.md, What is KYA.md, Buy-side roles.md, Sell-side roles.md, Infrastructure.md]
created: 2026-05-03
updated: 2026-05-03
---

# The Agentic Protocol Stack (KYAPay Framework)

**Source:** [kyapay.org/overview/the-agentic-protocol-stack](https://kyapay.org/overview/the-agentic-protocol-stack)
**Author:** KYAPay / AGNTCY consortium (Akamai, Apify, Consumer Reports, DataDome, Experian, Forter, Imperva, Skyfire, Sequentum)

## The core taxonomy: three rails, not two

The agentic commerce landscape is not "stablecoins vs. cards." KYAPay's framework identifies three specialized rails optimized for different trust/speed tradeoffs:

| Rail | Protocol | Analogy | Use case |
|------|----------|---------|----------|
| **Lightweight Micropayment** | x402 / H402 | Vending Machine | Anonymous, stateless API calls; sub-cent; no relationship |
| **High-Assurance** | AP2 / ACK | B2B Purchase Order | Regulated, high-value, auditable; verifiable credentials |
| **Relational** | KYAPay | Secure Checkout | Subscriptions, accounts, loyalty, repeat commerce |

x402's ceiling: by design it is anonymous and stateless. You cannot run a subscription, earn loyalty points, or manage returns through a vending machine.

## The Trust Gap: The Broken OAuth Handoff

The deepest infrastructure problem in agentic payments today. Current web identity uses two incompatible standards:

- **Human present** → OAuth Authorization Code Flow (RFC 6479): interactive, user proves identity to trusted provider
- **Machine acting alone** → Identity Assertion Grant (RFC 7521/7523): server asserts identity to another system

The "Trust Gap" is what happens between these: when a human hands a task to an agent, no standard exists for the middle ground. Current approaches either **impersonate** the user (agent logs in as them) or **identify the machine** (loses the user context entirely). Neither captures: *"I am Agent X, acting for User Y, authorized to do specifically Z."*

Three specific failures:
1. **Impersonation vs. Delegation** — no standard for bounded "acting on behalf of"
2. **Identity vs. Intent** — OAuth proves who, not what they authorized
3. **Static vs. Dynamic** — agent identity is ephemeral; existing model assumes permanent service accounts

## Identity tiers: the three-layer buy-side stack

KYA defines three distinct identity tiers that must all be resolved to authorize an agent transaction:

- **Human Principal** (`bid`) — the individual or business entity ultimately responsible; required for KYC/AML compliance
- **Buyer Agent** (`aid`) — the specific software process executing the task; ephemeral, identified by source IP or similar
- **Buyer Agent Platform** (`apd`) — the infrastructure hosting the agent (e.g., OpenAI, Anthropic, cloud provider); the business entity operators can apply reputation logic to

The KYA token is a composite credential carrying all three. A merchant can verify the entire chain of responsibility behind a single request.

## Sell-side structure

- **Seller Principal** — human/business owning the product; buyer needs this to know who they're doing business with
- **Seller Agent** — the API/MCP server directly interfacing with buyers; identifiable via domain + SSL cert
- **Seller Agent Platform** — the hosting infrastructure
- **CIAM (Customer Identity and Access Management)** — extended to treat agents as first-class identities; consumes KYA tokens to provision accounts without passwords/OTPs; enables bidirectional access (Human Principals can access agent-created accounts, agents can operate within human accounts)
- **Reverse Proxy/Bot Manager** — validates `kya` tokens at the network edge, allowing legitimate agentic traffic while blocking malicious bots

## New identity protocols emerging

**AGNTCY** (Cisco/Linux Foundation): overarching infrastructure stack providing a "Digital Passport" — persistent, portable agent identity based on W3C Decentralized Identifiers (DIDs) and Verifiable Credentials (VCs). Agent carries its identity and permissions across platforms, clouds, and organizational boundaries.

**MCP-Identity (MCP-I)**: secures the agent-to-tool vertical with granular delegation ("I can read your calendar but not delete events"), verified identity attributes, and edge enforcement using Agent DIDs.

## KYAPay token primitives

Three JWT-based token types for different commerce interactions:
- `kya` — identity only; agent creates an account with a merchant (first visit)
- `pay` — payment only; known agent authorizes a specific payment (recurring/subscription)
- `kya-pay` — combined; simultaneous identity + account creation + payment authorization in one atomic step ("Secure Guest Checkout")

## The cooperative stack

| Layer | Protocol | Role |
|-------|---------|------|
| Agent-to-tool | MCP | "USB-C port" — universal tool access |
| Agent-to-agent | A2A | "Yellow Pages" — peer discovery and task delegation |
| Portable identity | AGNTCY | "Digital Passport" — cross-platform identity |
| Micropayment | x402 | "Vending Machine" — anonymous instant payments |
| High-assurance | AP2 / ACK | "B2B Purchase Order" — auditable high-value commerce |
| Relational commerce | KYAPay | "Secure Checkout" — accounts, subscriptions, relationships |

## Why this matters

The stablecoin vs. card debate focuses on the payment layer (bottom of the stack). KYA and the trust infrastructure above it are arguably more important: without resolved agent identity, neither rail can scale safely. A merchant who can't verify who authorized a $500 purchase has no basis for dispute resolution regardless of which rail processed it.

## Open questions

- Will KYA/KYAPay gain adoption against the Visa/Mastercard "Trusted Agent" programs building similar identity infrastructure?
- Which entity becomes the dominant "Identity Token Issuer" — the payment networks, Big Tech platforms, or neutral third parties?
- Does the three-rail taxonomy hold, or does one rail (likely Relational) absorb the others as trust infrastructure matures?

## Related pages

- [[know-your-agent]] — concept page
- [[ap2]] — High-assurance rail
- [[x402]] — Lightweight rail
- [[agentic-protocol-stack-kyapay]] — this page
- [[catena-labs]] — AI-native institution solving the identity anchor problem
- [[concepts/agentic-commerce]]
