---
title: "Payments for AI Agents — Natural.co"
type: summary
topic: agentic-money
source_type: company-blog
tags: [infrastructure, agentic-commerce, wallet, b2b-payments]
sources: ["Payments for AI agents.md"]
created: 2026-04-26
updated: 2026-04-26
---

# Payments for AI Agents — Natural.co

**Source:** Natural.co homepage, www.natural.co
**URL:** https://www.natural.co/

Product overview for Natural — the agentic payments platform founded by Kahlil Lalji.

## What Natural does

Natural is a full-stack agentic payments platform that handles the entire payments lifecycle for AI agents — from holding funds through execution — across any financial rail.

> "You build agents, we orchestrate payments."

## Six products

| Product | Description |
|---------|-------------|
| **Wallet** | FDIC-insured accounts for agents to hold, receive, and send funds |
| **Pay** | Single tool call for agent-initiated payments; Natural handles routing complexity |
| **Collect** | Collect funds from customers, vendors, and agents via payment links, phone, or direct |
| **Credit** | Agent access to credit for autonomous spend without pre-funding |
| **Bill** | Agent billing of customers based on outcomes, success, tokens, or other defined criteria |
| **Transfer** | Agentic transfers between Natural and external accounts of all types |

## Integration

Simple code example:
```python
agent = await natural_client.agents.create(
    name="Carrier Payment Agent v2.1",
    description="Autonomous agent that pays delivery carriers",
    limits={"per_transaction": 100_000},
    permissions=["payments.create"]
)
```

Integration via: API, MCP, or tool calls.

## Design principles

- **Intelligent** — handles onboarding, verification, settlement in background
- **Fluid** — real-time settlement, every transaction unlocks instant value
- **Expansive** — collapses different rails, speeds, rules into one unified layer
- **Resilient** — move money without risk; Natural handles complexity

## Investors (selected quotes)

From Forerunner Ventures: *"Agents now hold the right to rewrite the rules of financial participation. You won't find a better team."*

Multiple investors independently note:
- "Agentic payments will dwarf human-initiated payments within a decade"
- "Natural is pioneering this frontier"
- "AI financial services will be a $1 trillion revenue market in ten years"

## Significance

Natural is the most complete agentic payments stack seen in this wiki — covering wallets, payments, collections, credit, billing, and transfers through a unified agent-native API. The FDIC-insured wallet + credit product combination directly addresses the spend control problem identified in the [[agentic-payments-memo-natural]].

The outcome-based billing product (**Bill**) is particularly interesting: it allows agents to charge customers based on results achieved, not just API calls — a business model not possible with traditional payment infrastructure.

## Related pages

- [[natural]]
- [[agentic-payments-memo-natural]]
- [[session-payments]]
- [[agentic-commerce]]
- [[slash]]
- [[era]]
