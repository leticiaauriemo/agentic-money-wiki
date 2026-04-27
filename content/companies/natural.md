---
title: "Natural"
type: company
topic: agentic-money
tags: [infrastructure, wallet, b2b-payments, agentic-commerce, payment-processor]
stage: private
hq: Unknown
sources: ["Payments for AI agents.md", "Agentic payments memo.md"]
created: 2026-04-26
updated: 2026-04-26
---

# Natural

**One-line:** Full-stack agentic payments platform — the "Stripe for AI agents" — offering wallets, payments, collections, credit, billing, and transfers through a single agent-native API.

## What they're building

Natural provides every component of the payments stack that an AI agent needs to operate financially: a funded wallet to hold money, tools to pay other agents/businesses/consumers, the ability to collect funds, access to credit for autonomous spend, outcome-based billing, and transfers across all external account types.

The thesis (from founder Kahlil Lalji's seed memo): agents can already negotiate, hire, and manage — but the moment money needs to move, the workflow breaks and a human must step in. Natural eliminates that human bottleneck.

## Six products

| Product | Description |
|---------|-------------|
| **Wallet** | FDIC-insured accounts for agents to hold, receive, send |
| **Pay** | Single tool call → Natural handles routing and compliance |
| **Collect** | Inbound funds from customers, vendors, agents |
| **Credit** | Agent access to credit; no pre-funding required |
| **Bill** | Charge customers based on outcomes, tokens, or defined criteria |
| **Transfer** | Move funds between Natural and any external account type |

## Relevance to agentic money

Natural is the most complete purpose-built agent payments stack in this wiki — building what they argue Stripe cannot: rails designed from first principles for machines, not humans.

Three payment types addressed: **A2A** (agent-to-agent), **A2B** (agent-to-business), **A2C** (agent-to-consumer). Two macro categories: Commerce and Labor (including displaced payroll volume as agents replace contractors).

The **Bill** product is particularly novel: outcome-based billing (charge per result, not per API call) is a business model that traditional payment infrastructure cannot support but that AI agent workflows naturally fit.

## Funding & traction

- Seed funded (raised using Kahlil Lalji's 15-page memo)
- Investors include Forerunner Ventures and others (full list not public)
- Starting with ACH rails; expanding to other rails

## Key people

- **Kahlil Lalji** — founder/CEO; author of the agentic payments seed memo

## Investor thesis (selected quotes)

- Forerunner: *"Agents now hold the right to rewrite the rules of financial participation."*
- Multiple: *"Agentic payments will dwarf human-initiated payments within a decade."*
- *"AI financial services will be a $1 trillion revenue market in ten years."*

## Distribution strategy

Three-pronged:
1. **YC-focused** — 80%+ of recent YC batches are AI-first; target before they scale
2. **PayPal-esque** — own the sending account; push stablecoin to receivers; force KYB to claim funds (PayPal's original growth model)
3. **AP/AR wedge** — automate accounts payable/receivable as entry point; build generalizable rails on top

## Open questions

- What is Natural's current live transaction volume?
- Which payment rails are live beyond ACH? (Stablecoin, card, wire?)
- How does Natural handle agent identity/KYA for its Wallet product?
- What is Lalji's background? (Prior company experience)
- Who are the notable enterprise customers?

## Sources

- [[payments-for-ai-agents-natural]]
- [[agentic-payments-memo-natural]]
