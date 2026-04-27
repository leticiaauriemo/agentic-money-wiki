---
title: "ACP — Agentic Commerce Protocol"
type: rail
topic: agentic-money
tags: [agentic-commerce, payment-processor, infrastructure, identity-kyc]
sources: ["Agent Ready.md", "Agentic commerce services.md", "Agentic Commerce Solutions for Businesses.md"]
created: 2026-04-26
updated: 2026-04-26
---

# ACP — Agentic Commerce Protocol

**Type:** Application-layer commerce protocol
**One-line:** OpenAI's open standard for how AI agents complete purchases on behalf of buyers — covering product discovery, checkout session negotiation, and delegated payment credential handling.

## How it works

ACP defines three specifications that together form a complete agentic commerce pipeline:

| Spec | Purpose | Parties |
|------|---------|---------|
| **Product feed** | How merchants expose their catalog for AI discovery | AI platform ↔ Merchant |
| **Agentic checkout** | How AI agents create checkout sessions and complete orders | AI platform ↔ Merchant |
| **Delegated payment** | How AI platforms securely obtain payment credentials from PSPs | AI platform ↔ PSP |

### Flow (end to end)

1. AI platform (ChatGPT, Perplexity) discovers merchant products via **product feed**
2. AI agent creates a checkout session via **agentic checkout** spec; merchant server responds with payment provider details
3. AI platform requests a **delegated payment token** from the PSP (PayPal/Braintree)
4. PSP issues a **one-time-use token** bound to: specific merchant ID, max amount, currency, expiry
5. AI platform sends the token to the merchant's MCP server `complete_checkout` tool
6. Merchant processes the token via existing payment integration — buyer credentials never leave the PSP

The one-time-use token model is the key trust mechanism: the AI platform never sees raw buyer payment credentials.

## Settlement speed & cost

Depends on the underlying PSP (PayPal/Braintree). ACP is a protocol layer, not a settlement rail — it delegates settlement to existing payment infrastructure.

- No chargebacks bypassed (traditional card chargeback rules apply)
- No stablecoin settlement (fiat-native via existing PSP integrations)
- Fraud protection and Purchase/Seller Protection carry over from the PSP

## Who controls it

Developed and maintained by **OpenAI**. Spec published at developers.openai.com/commerce/specs/checkout. OpenAI positions it as an open standard for the industry.

## Agent-friendliness

High for structured commerce flows (buy a specific product). ACP is purpose-built for AI agents operating in a supervised or delegated shopping context.

Lower for open-ended micropayments or A2A payments — ACP is commerce-oriented (products, carts, checkout), not a general-purpose machine payments protocol.

## Who is implementing it

| Implementer | Role | Details |
|-------------|------|---------|
| **[[paypal]]** / Braintree | PSP (delegated payment layer) | Issues one-time-use nonces; tracks AI transactions via `facilitator_details` |
| **[[stripe]]** | PSP + co-author | ACP implementation in Agentic Commerce Suite |
| **ChatGPT** | AI platform (buyer) | Native checkout in ChatGPT via ACP |
| **Perplexity** | AI platform (buyer) | Confirmed ACP partner (PayPal) |
| **Google** | AI platform (buyer) | Confirmed ACP partner (PayPal) |

## How ACP relates to other protocols

| Protocol | Designed for | Settlement |
|----------|-------------|-----------|
| **ACP** | Structured commerce (products, carts, checkout) | Fiat via PSP (PayPal, Braintree, Stripe) |
| **[[ap2]]** | Enterprise mandate-based agent payments | Card networks via cryptographic mandates |
| **[[x402]]** | Permissionless API micropayments | Stablecoin (USDC on Base) |
| **[[mpp]]** | High-frequency agent loops | Stablecoin + Stripe cards |

ACP and AP2 are the two "trusted commerce" protocols (identity-preserving, existing rails). x402 and MPP are the two "permissionless" protocols (crypto-native, no merchant agreements needed).

## Regulatory status

ACP operates on existing fiat rails (card networks, ACH) via PayPal/Braintree/Stripe, so it inherits existing payment regulatory frameworks. No new regulatory questions beyond standard card network compliance and PSP licensing.

## Open questions

- Will ACP become a true open standard with governance outside OpenAI, or remain OpenAI-controlled?
- How does ACP handle disputes when an agent makes a purchase the user didn't intend?
- Will other PSPs (Adyen, Square, etc.) implement ACP's delegated payment spec?
- Does ACP have a path to stablecoin settlement, or is it permanently fiat-native?

## Sources

- [[agent-ready-paypal]] — PayPal/Braintree ACP implementation (technical spec)
- [[agentic-commerce-services-paypal]] — Store Sync + Agent Ready overview
- [[stripe]] — Stripe as ACP co-implementer
