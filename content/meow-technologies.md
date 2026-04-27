---
title: "Meow Technologies"
type: company
topic: agentic-money
tags: [infrastructure, bank-api, wallet, agentic-commerce, compliance]
founded: 2021
stage: private
hq: San Francisco, CA
sources: ["Meow Technologies launches the first agentic banking platform for AI agents.md"]
created: 2026-04-25
updated: 2026-04-25
---

# Meow Technologies

**One-line:** Launched April 2026 as "the world's first agentic banking platform" — enabling AI agents to autonomously open business bank accounts, issue cards, send payments, manage invoices, and handle account activity without human authorization by default.

## What they're building

Meow enables AI agents (Claude, ChatGPT, Cursor, Gemini) to access full business banking functionality via MCP integration. Unlike competitors (Stripe, Mastercard, PayPal, Google, Visa) which focus on specific payment actions, Meow's scope covers the entire account lifecycle:

- Autonomously open business bank accounts
- Issue virtual and physical cards
- Send payments (ACH, wire)
- Manage invoicing
- Handle day-to-day account activity

**Permissioned architecture** — despite broad scope, Meow defaults to no unilateral money movement. Every transfer requires an initiator-and-approver workflow. Configurable by risk tolerance:
- High-volume e-commerce: higher thresholds, fewer approval steps
- Conservative firms: human sign-off above any material amount

Every transaction is logged and fully auditable. Transfer limits, 2FA, and role-based permissions enforced at infrastructure level.

## Relevance to agentic money

Meow occupies the most permissive position in the agentic payments landscape. While Visa/Mastercard/Google/Stripe focus on payments within existing account structures, Meow lets agents **own and operate** bank accounts. If agents are to become true economic actors, they need what Meow is building — not just payment credentials, but accounts.

The article notes: "Banking will rapidly shift away from apps and dashboards toward a seamless, automated experience through AI agents."

Observation: Fintech firms that build agent financial rails earliest will have a "structurally advantaged position."

## Funding & traction

- Founded: 2021
- Raised: ~**$30 million** in venture funding
- Assets held on platform: **$1+ billion**
- Announced: April 8, 2026
- Investors: Tiger Global, QED Investors, Lux Capital, Slow Ventures, Coinbase Ventures, Gemini Frontier Fund

## Key people

- **Brandon Arvanaghi** — CEO; former cryptocurrency engineer

## Products / offerings

- Agentic banking platform (MCP-integrated)
- Business bank account management via agents
- Card issuance and management
- Payment execution (ACH)
- Invoice management
- Permissioning and approval workflow infrastructure

## Partnerships & integrations

- Claude (Anthropic), ChatGPT (OpenAI), Cursor, Gemini — supported agent platforms
- MCP (Model Context Protocol) — primary integration standard (6,400+ registered servers as of Feb 2026)

## Open questions

- What banking license/charter does Meow hold, or which bank is its partner?
- How does Meow handle regulatory compliance when an agent initiates a cross-border payment?
- What is the incident/fraud rate on agent-initiated transactions so far?
- How does Meow's full-account model coexist with [[ap2]] and [[mpp]] standards?

## Sources

- [[meow-technologies-agentic-banking-launch]]
