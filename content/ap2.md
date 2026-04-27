---
title: "AP2 (Agent Payments Protocol)"
type: rail
topic: agentic-money
tags: [infrastructure, stablecoin, card-rails, identity-kyc, compliance, agentic-commerce]
sources: []
created: 2026-04-25
updated: 2026-04-25
---

# AP2 (Agent Payments Protocol)

**Type:** Open agent payment protocol (fiat + crypto)
**One-line:** Google's open protocol for secure agent-initiated payments, using cryptographically signed "Mandates" (Verifiable Credentials) to prove authorization and support both card rails and stablecoins.

## How it works

AP2's central innovation is the **Mandate** — a tamper-proof, cryptographically signed Verifiable Credential (VC) that encodes exactly what an agent is authorized to buy, at what price, and under what conditions. Two transaction modes:

- **Human-present**: User reviews agent's cart and signs a Cart Mandate — an unchangeable record of the approved items and price
- **Human-not-present**: User pre-signs an Intent Mandate upfront (e.g. "buy concert tickets the moment they go on sale"), giving the agent delegated authority within defined bounds

Every transaction produces a non-repudiable cryptographic audit trail, designed to resolve disputes and satisfy compliance requirements.

## Settlement speed & cost

Supports pull payments (credit/debit cards) today; roadmap includes push payments (real-time bank transfers, stablecoins, digital currencies).

## Who controls it

Built by Google, open-source at [google-agentic-commerce/AP2](https://github.com/google-agentic-commerce/AP2). Can be used as an extension of the Agent2Agent (A2A) protocol and MCP.

## Agent-friendliness

High, and uniquely focused on the **authorization and liability** problem that x402/MPP leave open. Mandates create verifiable proof that a user delegated specific authority to an agent — critical for compliance and dispute resolution at scale.

## Who is building on it

60+ partner organizations including:
- Mastercard, American Express, PayPal — payment networks
- Adyen, Worldpay, UnionPay — payment processors
- Salesforce, ServiceNow, Intuit — enterprise software
- Coinbase — crypto extension (launched the A2A x402 extension jointly)
- Ethereum Foundation, MetaMask — crypto rails

## Live stats

No public explorer or transaction dashboard as of 2026-04-25. Protocol is in early implementation phase; developer tooling and code samples available but not yet widely deployed at scale.

## Regulatory status

AP2's Mandate/VC model appears designed with compliance in mind — the audit trail and explicit authorization records address the authorization, authenticity, and accountability gaps that regulators have flagged for agentic payments. Most aligned with regulatory requirements of the three main protocols.

## Related concepts

- [[x402]] — Coinbase's HTTP-native protocol; AP2 has an x402 crypto extension
- [[mpp]] — Stripe + Tempo's machine payments protocol
- [[stablecoin]]

## Open questions

- Will AP2 achieve interoperability with x402 and MPP, or will these protocols fragment?
- When will AP2 launch a public transaction explorer?
- How does the Mandate model interact with existing card network chargeback rules?
- Is the 60-partner coalition enough to make this the dominant standard?
