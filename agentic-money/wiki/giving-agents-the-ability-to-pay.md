---
title: "Giving Agents the Ability to Pay"
type: summary
topic: agentic-money
source_type: company-blog
tags: [agentic-commerce, wallet, payment-processor, infrastructure]
sources: [Giving agents the ability to pay.md]
created: 2026-05-03
updated: 2026-05-03
---

# Giving Agents the Ability to Pay

**Source:** [Stripe Blog](https://stripe.com/blog/giving-agents-the-ability-to-pay), published 2026-04-29
**Author:** Dan Hill

## What launched

Stripe launched two new products on April 29, 2026:

1. **Link's wallet for agents** — consumer-facing; gives personal AI agents programmatic access to Link (Stripe's consumer wallet, 200M+ users), generating one-time-use cards or Shared Payment Tokens (SPTs)
2. **Stripe Issuing for agents** — developer/business-facing; APIs for businesses to build custom agentic wallets and cards

---

## How Link's wallet for agents works

1. **OAuth grant** — consumer grants agent access to their Link wallet via standard OAuth flow
2. **Spend request** — agent creates a spend request, providing transaction context; requests either a one-time-use card or an SPT
3. **Consumer approval** — consumer receives notification and approves on the web or via Link iOS/Android app; agent never sees raw payment credentials
4. **Credential issuance** — Link returns the one-time-use card or SPT to the agent
5. **Tracking** — consumer can track agent spending and manage connected agents in Link

**Credential scoping:** Both card and machine-native flows can be scoped with controls — amount, currency, merchant.

**Coming soon:** Agentic tokens, stablecoins, and other payment types. Plans to let people set spending limits and choose when agents can act without additional approval.

## Who it's for

- Consumers who want to enable personal AI agents (example: OpenClaw) to make authorized purchases
- Developers building consumer-facing agents (personal assistants, shopping agents) — removes need to build wallet infrastructure from scratch
- Link's 200M+ consumer base as built-in distribution

---

## Stripe Issuing for agents

Businesses that want to build and customize their own agentic wallets and cards — not use Link's consumer flow.

**Capabilities:**
- Full Issuing API access for agentic spending and custom financial workflows
- Single-use virtual cards and fund storage
- Spending controls at the card level
- Transaction monitoring and authorization
- Advanced fraud tools
- Real-time visibility into card activity

**Use cases:**
- Developers automating own business spend (programmatic workflows, recurring purchases)
- Fintech providers embedding agent-issued cards for expense management
- Vertical SaaS platforms issuing agent cards to SMB customers under their own brand
- Marketplaces issuing cards to sellers for automated supplier payments, logistics, fulfillment

---

## Relationship to MPP

The Stripe blog notes that machine payment protocols ([[mpp]]) "are still gaining adoption" and that agents need to work with payment options sellers and consumers use today. Link's wallet for agents bridges this gap — using the existing card/bank infrastructure today, with stablecoins and other payment methods flagged as "coming soon."

This positions Link as the consumer trust layer for agent payments, sitting between agent (OAuth) and Stripe's payment infrastructure, independent of which underlying rail is used.

---

## Related pages

- [[stripe]] — issuer of these products
- [[mpp]] — the machine payment protocol these products complement
- [[meow-technologies]] — enterprise-side agent banking (different market segment)
- [[giving-agents-the-ability-to-pay]] — this page
