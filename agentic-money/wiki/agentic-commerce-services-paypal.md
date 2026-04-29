---
title: "PayPal Agentic Commerce Services — Overview"
type: summary
topic: agentic-money
source_type: company-blog
tags: [agentic-commerce, payment-processor, wallet]
sources: ["Agentic commerce services.md"]
created: 2026-04-26
updated: 2026-04-26
---

# PayPal Agentic Commerce Services — Overview

**Source:** PayPal Developer Documentation, docs.paypal.ai
**URL:** https://docs.paypal.ai/growth/agentic-commerce/overview

Developer overview of PayPal's two-product agentic commerce strategy.

## The two products

### Store Sync
Makes merchant products discoverable by AI shopping assistants and allows them to place orders directly into existing order management systems. Partners: **Wix, Cymbio, Commerce (BigCommerce + Feedonomics), Shopware**.

What it enables:
- Product catalog syndication to AI platforms
- AI-initiated cart operations (add/update/remove items)
- AI-completed purchases flowing into merchant's existing OMS
- Merchant retains brand control and customer relationship ownership

### Agent Ready
Payments foundation for accepting payments on AI platforms. See [[agent-ready-paypal]] for full technical spec.

## Four key benefits

1. **Easy setup** — connects through existing PayPal partners (Wix, Cymbio, etc.) rather than new integrations
2. **Better product discovery** — AI shopping assistants understand natural language queries, turn conversations into purchases
3. **Keep customer relationships** — merchants control brand appearance and customer communications for all AI-powered transactions
4. **Connect once, reach many** — single integration reaches multiple AI shopping platforms

## Access

Gated: merchants must complete a contact form at paypal.com/us/business/ai#form to request access from PayPal's AI team.

## The Cymbio connection

Store Sync partners with **Cymbio** — the company [[paypal]] acquired in 2026 as its trust/settlement layer for agentic commerce. This means Store Sync's product catalog syndication runs through PayPal's own acquired infrastructure, not a third-party.

## Significance

Store Sync + Agent Ready together represent PayPal's full-stack approach to agentic commerce: discovery layer (Store Sync, via Cymbio/partners) + payment execution layer (Agent Ready, via Braintree/ACP). The strategy preserves PayPal as the merchant-of-record while AI platforms handle the discovery and ordering interface.

## Related pages

- [[paypal]]
- [[agent-ready-paypal]]
- [[agentic-commerce-solutions-paypal]]
- [[agentic-commerce]]
- [[universal-commerce-protocol]]
