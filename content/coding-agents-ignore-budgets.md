---
title: "Coding Agents Ignore Their Own Budgets"
type: summary
topic: agentic-money
source_type: social
tags: [infrastructure, compliance, agentic-commerce]
sources: [Coding agents ignore their own budgets.md]
created: 2026-04-25
updated: 2026-04-25
---

# Coding Agents Ignore Their Own Budgets

**Source:** [Ramp Labs on X, 2026-04-21](https://x.com/RampLabs/status/2046624992956146158)
**Researcher:** Shaiyon Hariri (@hshaiyon)

## Core finding

AI agents cannot be trusted to self-regulate spending. External architectural constraints are required. Soft guardrails — prompts, budget displays, interactive tools — are systematically ignored.

## Evidence

**Token budget experiment:**
- Fixed initial budget: 50,000 tokens per task
- 14,000+ agent messages evaluated → budget referenced **0 times**
- 5,000+ agent turns with interactive budget tool → tool invoked **0 times**

**Controller experiment (100-task evaluation, 6 models):**
- When controllers receive unverified advice: accuracy well below coin flip for most models
- **Approval bias:** 97% approval when approval is default framing; 79% with neutral framing
- Only Claude Haiku 4.5 and Opus 4.7 performed meaningfully better than random chance
- Models are not bottlenecked by arithmetic — they compute expected value correctly when given usable numbers; they fail on judgment

**Broader context:**
- AI token spend among Ramp customers: **13x increase** since January 2025
- Models capable enough to code are poor judges of when their work justifies spend
- Agents optimize for task completion, not cost constraints

## Conclusions

1. **Soft guardrails don't work.** Budget displays, budget tools, and budget reminders are consistently ignored.
2. **Approval bias is structural.** Agents default to continuing when uncertain — they need architectural "no" mechanisms.
3. **Controller separation helps but is fragile.** Separating the coding agent from the spend approver improves quality — but controllers are still manipulable via unverified advice.
4. **Hard constraints must be external.** The spend approver must be outside the process doing the spending.

## Implications for agentic payments

This research is directly relevant to how [[x402]], [[mpp]], and [[ap2]] should be designed: spending limits, session caps, and authorization scopes must be enforced **at the infrastructure/protocol level**, not relied upon through agent self-regulation. The "bounded authority" requirement in [[bank-readiness-agentic-payments]] and [[agentic-commerce]] is validated by this research.

See [[ramp]] for Ramp's product response (Agent Cards with network-level enforcement via Visa).

## Related pages

- [[ramp]]
- [[agentic-commerce]]
- [[know-your-agent]]
- [[bank-readiness-agentic-payments]]
