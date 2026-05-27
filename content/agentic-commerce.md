---
title: "Agentic Commerce"
type: concept
topic: agentic-money
tags: [agentic-commerce, infrastructure, stablecoin, card-rails]
sources: ["Machine Economy 2030.md", "Is 2026 the Year of Agentic Payments?.md", "Agentic Commerce The Future of AI-Powered Shopping.md", "The Agentic Economy Will Be Massive. Agentic Commerce Won't.md"]
created: 2026-04-25
updated: 2026-04-25
---

# Agentic Commerce

**One-line:** Commerce where AI agents autonomously research, decide, and execute purchases on behalf of a human principal — shifting checkout from a human action to a programmatic event.

## How it works

Agentic commerce has three distinct modes (J.P. Morgan taxonomy):

1. **Agent-assisted discovery** — agent researches and presents options; human chooses and authorizes. Not truly agentic commerce, but the dominant form today.
2. **Agent-embedded commerce** — similar to social commerce; agent embedded in a platform completes purchase with human approval at checkout. Current leading edge.
3. **Autonomous purchasing** — agent completes purchase end-to-end without human approval at transaction time. Human sets policies upfront; agent executes within them. The emerging frontier.

The critical infrastructure requirement for mode 3: the agent needs an authorization mechanism (mandate, credential, or policy) that proves to merchants it has legitimate permission to spend on the user's behalf.

## Why it matters for agentic money

Agentic commerce is the demand-side driver for all the payment protocol infrastructure (x402, MPP, AP2). Without agents actually buying things, there's no market for agent payment rails. The key debate: **how big is the addressable market?**

**Bull case** (McKinsey, Galaxy, Deloitte): $3–5T globally by 2030; $17.5T by 2030; $50B market by 2028. Galaxy estimates $600M annualized by 2026.

**Bear case** (@robbiepetersen_ / Dragonfly): 95%+ of agentic deployments are commercial agents within organizations that don't transact autonomously — their costs are bundled into SaaS pricing, not granular micropayments. Consumer agents will remain research assistants that hand off to humans for authorization. Only "bottom-up" agents (OpenClaw-style) will truly transact, and only on crypto rails because they need permissionlessness.

## Commerce lifecycle autonomy map (May 2026)

Simon Taylor (FintechBrainFood, 2026-05-24) mapped each stage of the e-commerce journey to an autonomy level, arguing payments are the *least* impacted stage right now:

| Stage | Level | Key insight |
|-------|-------|-------------|
| Discovery | L2→L3 | Agents compare thousands of SKUs; structured catalog converts 2x better |
| Referral | L1→L2 | UCP carries intent; agents don't choose referral path autonomously |
| Intent | L1 | AP2 mandates exist in spec; live volume thin |
| Delegation | L1 | TAP/AP2/ACP/UCP protocols shipping but don't interoperate |
| Policy | L1 | Merchants defining agent policies unilaterally |
| Cart | L1→L2 | UCP April 2026 added cart capability; Walmart sees 77% abandonment inside ChatGPT |
| Payment | L1 | 95% of AI-driven commerce completes on merchant's own site |
| Fulfillment | L1 | UCP spec includes fulfillment events; identity linking beginning |

**Key data points (Q1 2026):**
- Shopify: AI-driven traffic 8x YoY, AI-powered orders 13x YoY
- Adobe: AI referrals convert 42% better (up from 31% holiday 2025)
- Walmart/ChatGPT: 1.18% conversion rate, 77% cart abandonment vs. 2.5–3% industry average
- eMarketer/Stripe: 95% of AI-platform-driven e-commerce completes off the AI platform

**Stripe's 5 levels of agentic commerce** (from 2025 annual letter):
- L1: Humans choose items, agents complete purchase
- L2: Agent researches, presents options, human chooses, agent buys
- L3: Human delegates ("buy coffee beans under $20"), agent executes
- L4: Agent manages complex tasks (inventory replenishment, subscriptions) with policies
- L5: Agent anticipates needs and buys proactively

**The audit trail problem:** No single entity sees the full transaction. Visa sees auth; Shopify sees cart; Google UCP sees checkout session; AI lab sees intent; merchant sees fulfillment. This compliance vacuum led Target to update its terms treating AI purchases as "authorized by you," and Amazon to get a federal injunction blocking Perplexity's Comet browser agent.

**FIDO Alliance convergence (April 2026):** Agentic Authentication Working Group launched with Google (AP2) and Mastercard (Verifiable Intent) as initial contributors. OpenAI joined FIDO's board. Signals protocol convergence beginning.

Source: [[commerce-for-ai-brainfood]]

## Current state (April 2026)

**Protocols live:**
- [[x402]] — 167.96M transactions, $49.51M volume, 519K buyers
- [[mpp]] — 50.7K transactions, $7.27K volume, 6.5K agents
- [[ap2]] — no public stats; still in early deployment

**Major network commitments:**
- [[mastercard]] — live transactions in Europe, Latin America, Southeast Asia (Agent Pay)
- [[visa]] — agentic commerce live in US + CEMEA; stablecoin cards in 50+ countries
- [[stripe]] — MPP launched March 2026; Agentic Commerce Suite with live merchant partners

**Reality check:** Most x402 activity may still be developer testing. Analyst @onchainlu reports "qualified sellers" (≥2 real transactions, ≥2 unique buyers) grew from <100 (Oct 2025) to >4,000 (April 2026) — significant growth but still nascent.

## Key friction points

1. **Trust** — consumers don't yet trust agents to spend autonomously
2. **Identity** — merchants can't verify agent authorization (see [[know-your-agent]])
3. **Regulatory uncertainty** — EFTA, Regulation E unclear for agent-initiated transactions
4. **Discovery** — agents can't find and compare what services are available to purchase
5. **Fraud models** — banks and networks trained on human behavior patterns

## Key players using / building this

- [[stripe]] — MPP, ACP, Agentic Commerce Suite
- [[visa]] — Visa Intelligent Commerce
- [[mastercard]] — Agent Pay
- [[ap2]] — Google's Mandate-based authorization framework
- [[merit-systems]] — discovery layer (AgentCash, x402scan, MPPscan)
- [[slash]] — agentic card issuance and spend control via MCP
- [[brex]] — internal enterprise agentic finance

## Related concepts

- [[x402]]
- [[mpp]]
- [[ap2]]
- [[know-your-agent]]
- [[stablecoin]]
- [[bank-readiness-agentic-payments]]

## Sources

- [[machine-economy-2030]]
- [[is-2026-year-agentic-payments]]
- [[agentic-commerce-future-shopping-jpmorgan]]
- [[the-agentic-economy-will-be-massive]]
