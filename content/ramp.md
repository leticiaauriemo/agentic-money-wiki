---
title: "Ramp"
type: company
topic: agentic-money
tags: [infrastructure, agentic-commerce, compliance, identity-kyc]
founded: 2019
stage: private
hq: New York, NY
sources: ["Agentic Payments Use Cases Risks & How to Get Started.md", "Coding agents ignore their own budgets.md", "Post by @RampLabs on X.md"]
created: 2026-04-25
updated: 2026-04-25
---

# Ramp

**One-line:** Corporate card and spend management platform building agentic AP, accounting, and policy automation — and publishing important research showing that AI agents cannot self-regulate spending without hard architectural constraints.

## What they're building

Ramp is extending its corporate spend management platform with three agentic products:

**Ramp Agents for AP (Accounts Payable):**
- Auto-codes line items against chart of accounts
- Checks 60+ fraud signals per invoice
- Surfaces card-eligible bills for cashback
- Recommends approvals
- Result: 7x fewer clicks for invoice processing

**Ramp Accounting Agent:**
- Codes transactions at point of swipe
- Auto-syncs to ERP
- Accrues transactions
- Result: 3.5x more transactions coded automatically, 98% accuracy

**Ramp Policy Agent:**
- Reviews every transaction against expense policy
- Auto-approves in-policy spend, escalates exceptions
- Result: 7x more out-of-policy spend caught, 4–5 hours/week reclaimed per team

**Ramp Agent Cards** (early access):
- Single-use credentials via Visa Intelligent Commerce
- Locked to exact transaction at network level
- Token expires and cannot be reused or redirected

**Ramp AI Token Spend Management:**
- Tracks AI token spend for customers
- Finding: AI token spend increased **13x** among Ramp customers since January 2025

## Relevance to agentic money

Ramp Labs published the most rigorous research to date on **why agents cannot self-regulate their spending**. Key findings:
- 14,000+ agent messages evaluated without ever referencing the budget
- 5,000+ agent turns with interactive budget tool — tool invoked 0 times
- With unverified advice, controller model accuracy falls below coin flip
- Only hard architectural constraints (not prompt-based guardrails) reliably constrain agent spending
- Approval bias: agents approve 97% of the time when approval is the default framing

This research is important for the entire agentic payments ecosystem: it establishes that **spending limits must be enforced at the infrastructure level**, not trusted to agent self-regulation.

## Key stats

- 13x increase in AI token spend among customers (Jan 2025 → Jan 2026)
- 7x fewer invoice processing clicks
- 3.5x more transactions coded automatically
- 98% accuracy on auto-coded transactions
- 7x more out-of-policy spend caught
- 4–5 hours/week reclaimed per team
- 97% approval bias when default framing used

## Key people

- Shaiyon Hariri (@hshaiyon) — researcher, RampLabs

## Products / offerings

- Ramp corporate cards + spend management (core)
- Ramp Agents for AP
- Ramp Accounting Agent
- Ramp Policy Agent
- Ramp Agent Cards (Visa Intelligent Commerce, early access)
- Ramp AI Token Spend Management

## Partnerships & integrations

- [[visa]] — Ramp Agent Cards use Visa Intelligent Commerce
- [[mastercard]] — AP2 platform mentioned as network-level restriction mechanism

## Open questions

- Will Ramp extend into [[x402]] or [[mpp]] rails, or remain card-centric?
- Does Ramp's research on agent budget failures generalize to consumer agents (not just coding agents)?
- What is Ramp's agent card fraud rate in production?

## Sources

- [[agentic-payments-use-cases-ramp]]
- [[coding-agents-ignore-budgets]]
- [[post-ramplabs-x]]
