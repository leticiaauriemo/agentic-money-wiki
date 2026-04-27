---
title: "Agentic Banking"
type: concept
topic: agentic-money
tags: [bank-api, agentic-commerce, infrastructure, compliance]
sources: ["Agentic banking How AI agents are transforming finance.md", "Agentic Banking When Money Starts Thinking in Systems.md", "Banks Shift AI From Chatbots to Autonomous Money Movement.md"]
created: 2026-04-26
updated: 2026-04-26
---

# Agentic Banking

**One-line:** The shift from AI-powered chatbots in banking (reactive, question-answering) to AI agents that autonomously execute multi-step financial tasks — initiating payments, managing cash positions, processing invoices — without per-action human approval.

## How it works

Agentic banking operates on a **"human on the loop"** model:
1. Humans define policies, limits, and goals (e.g., "maintain $50K minimum cash balance, auto-approve invoices under $5K from approved vendors")
2. AI agents monitor, decide, and execute continuously within those constraints
3. Humans review outcomes and adjust policy; agents escalate edge cases

This contrasts with **"human in the loop"** banking (agent drafts, human clicks approve) and **full autonomy** (no human oversight).

## Two deployment paths

**Top-down (enterprise):** Financial institutions deploy agents internally for compliance, treasury, AP, fraud monitoring. Agents act within existing banking infrastructure. This is ~95% of current deployments (per Robbie Petersen's research).

**Bottom-up (agent-native):** New platforms (Meow, Catena Labs, Era) built for agents as the primary account holder. Agents open accounts, issue cards, initiate transfers — humans are the policy-setter, not the operator.

## Live examples

| Institution | Product | Performance |
|-------------|---------|-------------|
| Commerzbank | "Ava" | 75% autonomous resolution |
| ABN AMRO | "Anna" | 50%+ automation of millions of interactions |
| Bradesco | "BIA" | 82% first-level resolution |
| Virgin Money | "Redi" | 90%+ task delivery rate |
| Ramp | Agents for AP | 3.5x auto-coding, 98% accuracy |
| Brex | Audit/Review Agents | Policy-based auto-approval |

## Key blockers

1. **Fragmented legacy data** — agents need unified data foundation; siloed systems prevent autonomous operation
2. **Governance frameworks** — bounded authority, explainability, provenance, identity/permissions
3. **Fraud model mismatch** — "human=good, bot=bad" breaks when bots are authorized agents
4. **Regulatory clarity** — EFTA and consumer protection rules written for humans, not agents

## Agentic account types (emerging concept)

Jules Origliasso proposes account types defined by intelligence role:
- **Policy accounts** — enforce spending rules
- **Project accounts** — fund-bounded deliverables  
- **Agent accounts** — autonomous operational budgets
- **Autonomous treasury accounts** — self-optimizing liquidity

## Current state

Production deployments exist for internal banking operations (compliance, fraud, AP). Consumer-facing agentic banking (agents as primary account holder) is at early commercial stage: [[meow-technologies]] (April 2026), [[catena-labs]] (building), [[era]] (SEC-regulated investment management).

## Key players

- [[meow-technologies]] — first agentic banking platform for AI agents
- [[catena-labs]] — AI-native financial institution (Sean Neville)
- [[era]] — SEC-regulated autonomous personal finance
- [[ramp]] — agentic corporate finance
- [[brex]] — intelligent finance agents

## Related concepts

- [[know-your-agent]]
- [[bank-readiness-agentic-payments]]
- [[coding-agents-ignore-budgets]]
- [[agentic-commerce]]
