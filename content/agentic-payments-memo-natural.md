---
title: "Agentic Payments Memo — Natural.co Seed Memo"
type: summary
topic: agentic-money
source_type: analysis
tags: [infrastructure, agentic-commerce, b2b-payments, identity-kyc, compliance]
sources: ["Agentic payments memo.md"]
created: 2026-04-26
updated: 2026-04-26
---

# Agentic Payments Memo — Natural.co Seed Memo

**Source:** natural.co/blog/agentic-payments-memo
**Author:** Kahlil Lalji (founder, Natural)
**URL:** https://www.natural.co/blog/agentic-payments-memo

The 15-page seed memo Kahlil Lalji wrote before founding [[natural]] — used to raise the seed round. Remains the clearest first-principles analysis of why agentic payments need new infrastructure.

## The core premise

> "Today, agents can negotiate trucking loads, hire contractors, manage procurement and sales, but the second money needs to move, the workflow breaks. A human has to step in to execute the payment."

This is a temporary state. Natural is building the rails to make it permanent.

## Three payment types

| Type | Description | Example |
|------|-------------|---------|
| **A2A (Agent-to-Agent)** | Two autonomous systems exchanging value | Design agent paying engineering agent on same project |
| **A2B (Agent-to-Business)** | Agent paying a legacy business system | Browser agent completing purchase at traditional checkout |
| **A2C (Agent-to-Consumer)** | Agent sending funds to individuals | Finance agent making Zelle/Venmo-equivalent P2P transfers |

Two macro categories: **Commerce** (exchange of goods/services) and **Labor** (displaced payroll volume).

## Five structural problems

### 1. Traditional rails are too slow and costly
- Human-speed rail design: card auth holds, 1-3 day ACH clearing, FX overhead
- Multi-agent architectures need sub-second payment finality (design sub-agent delivers work in <5 min → must be paid in real-time)
- International transactions will be 10-100x more common; current international ACH costs $20+ vs. $2 domestic

### 2. Dispute arbitration is unclear
- Traditional model: issuer arbitrates; checks if authorized user initiated transaction
- Agent problem: what happens when agent makes a valid-but-wrong decision? (books 12-hour layover flight; user disputes)
- Who is liable: the agent builder, the platform, or the user who deployed the agent?

### 3. Identity is hard to manage
- Human counterparty evaluation: reviews, internet presence, known brands
- Agent-to-agent: purely programmatic, non-deterministic set of potential counterparties
- Need: a new method for uniquely verifying counterparty trustworthiness (see [[know-your-agent]], [[erc-8004-trustless-agents]])

### 4. Payments quickly become global
- Agents optimize for best vendor globally, not convenience-limited to domestic
- International share of agent transactions will be 10-100x current human rates
- Requires: low-cost, low-latency global rails without FX overhead

### 5. Existing risk controls break
- Card networks use ~3000ms authorization windows with models trained on human behavior
- Agent transaction patterns will look different from human patterns
- New fraud vectors, new datasets required

## Key opportunities

**Controllable wallets** — agents need an infinite number of purpose-specific wallets with JIT funding; prevents large liability exposure.

**Rules & controls** — deterministic guardrails injected via "system prompt": spending limits, approved/blocked counterparties, human approval requirements — at org, wallet, or transaction level.

**Authorization tools** — real-time payment authorization for agent-to-agent calls with <3000ms latency (equivalent to card auth speed today).

**Observability + tracing** — decision and event logging for both non-deterministic and deterministic outcomes; supports backtesting and audit.

## Distribution strategy

1. **YC-focused** — targeting AI-native startups (80%+ of recent YC batches); become the payment layer before these companies scale
2. **PayPal-esque** — own the sending account; push stablecoin to receiving wallets; recipients complete KYB to claim funds (PayPal's original growth engine adapted for agents)
3. **AP/AR wedge** — automate existing accounts payable/receivable workflows (OCR → approval → payment) as entry point; build generalizable rails on top

## The Stripe risk

> "If you believe that most transaction volume will eventually shift away from humans and towards autonomous systems then you come to the conclusion that you need to build purposefully around that and that only."

Stripe's current agent tools (dashboard automation, single-use card provisioning) are useful but address commerce only. They're not built for the full A2A, A2B, A2C taxonomy.

## Significance

This memo is the most rigorous public analysis of why existing payments infrastructure fails for agents, and what purpose-built agent rails need to do. It frames the market as a "once-in-a-generation" opportunity analogous to Stripe's 2010 moment — but for machines rather than internet developers.

The labor market thesis is underexplored by most agentic payments players: if agents displace $14.7T in US AGI and $700B+ in contractor payments, the payroll rails need to be rebuilt for AI.

## Related pages

- [[natural]]
- [[payments-for-ai-agents-natural]]
- [[session-payments]]
- [[know-your-agent]]
- [[headless-merchants]]
- [[bank-readiness-agentic-payments]]
- [[agentic-payments-buzz-real-gap]]
