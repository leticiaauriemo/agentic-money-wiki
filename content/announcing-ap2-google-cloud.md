---
title: "Announcing Agent Payments Protocol (AP2) — Google Cloud Blog"
type: summary
topic: agentic-money
source_type: company-blog
tags: [infrastructure, agentic-commerce, compliance, identity-kyc]
sources: ["Announcing Agent Payments Protocol (AP2)  Google Cloud Blog.md"]
created: 2026-04-25
updated: 2026-04-25
---

# Announcing Agent Payments Protocol (AP2) — Google Cloud Blog

**Source:** [Google Cloud Blog](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol)
**Authors:** Stavan Parikh (VP/GM, Payments, Google) & Rao Surapaneni (VP/GM, Business Applications Platform, Google Cloud)
**Published:** 2025-09-16

## What AP2 is

AP2 is a payment-agnostic protocol for AI agent-initiated transactions, built as an extension of Agent2Agent (A2A) and Model Context Protocol (MCP). Co-developed with **60+ partner organizations**.

## The problem AP2 solves

Current payment systems assume humans click "buy" directly. When autonomous agents initiate transactions, there's no trust anchor, no audit trail, and no mechanism for merchants to verify the user intended the purchase.

## How it works: Mandate model

AP2 uses cryptographically-signed **Mandates** as verifiable credentials:

- **Intent Mandate** — user grants an agent authority to transact (pre-authorized scope)
- **Cart Mandate** — unchangeable record of items and price (tamper-resistant)

Together they create a non-repudiable audit trail linking every transaction back to user intent.

## Two transaction types

1. **Human-present** — real-time purchase; human signs Cart Mandate directly
2. **Human-not-present (delegated)** — pre-authorized Intent Mandate; agent generates Cart Mandates within scope without requiring per-transaction human approval

## Three commerce experiences enabled

1. **Smarter shopping** — agents monitor and execute purchases based on conditions (e.g., buy when price drops below $X)
2. **Personalized offers** — merchant agents create dynamic bundles for specific user contexts
3. **Coordinated tasks** — agents booking travel across multiple systems simultaneously

## Partner ecosystem (60+ organizations)

**Payments:** Adyen, American Express, Ant International, Coinbase, JCB, Mastercard, PayPal, Revolut, UnionPay International, Worldpay, Airwallex, BVNK, Checkout.com, DLocal, Ebanx, Payoneer
**Commerce:** Etsy, Shopee
**Technology:** Google, Salesforce, ServiceNow, Dell, Okta, MetaMask, Mesh, Lightspark, Eigen Labs, Ethereum Foundation, Mysten Labs
**Consulting:** Accenture, Deloitte, PwC

## Web3 extension

A2A x402 extension — developed with Coinbase, Ethereum Foundation, MetaMask — provides crypto-native payment support within the AP2 framework.

## Related pages

- [[ap2]]
- [[mastercard]]
- [[coinbase]]
- [[know-your-agent]]
- [[agentic-commerce]]
