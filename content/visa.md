---
title: "Visa"
type: company
topic: agentic-money
tags: [card-rails, infrastructure, agentic-commerce, stablecoin, identity-kyc]
founded: 1958
stage: public
hq: San Francisco, CA
sources: ["Visa advances agentic commerce with developer updates.md", "Visa Intelligent Commerce for Agents.md", "Thread by @fintechfrank.md"]
created: 2026-04-25
updated: 2026-04-25
---

# Visa

**One-line:** Adapting its global card rails for agentic commerce via MCP-based developer tools and a tokenization framework, while settling $4.6B+ annualized stablecoin volume — still in pilot but moving fast.

## What they're building

Visa's agentic commerce strategy operates through **Visa Intelligent Commerce**, a platform offering four integrated services for agent-initiated payments:

1. **Tokenized credentials** — credentials bound to a specific agent, usable only by that agent for purchases on behalf of a user
2. **Authentication controls** — ensuring user authenticated the original agent instruction
3. **Payment controls** — aligning agent actions with the user's authenticated instructions (scope limiting)
4. **Commerce signals** — tracking purchases and managing disputes

Developer tooling:
- **Visa MCP Server** (in pilot) — enables AI agents to connect to Visa APIs via Model Context Protocol without hand-coding API calls; moves from idea to prototype in hours not weeks
- **Visa Acceptance Agent Toolkit** (in pilot) — prebuilt agent workflows for Acceptance Invoicing and Pay By Link using plain-language prompts; no code required

## Relevance to agentic money

Visa has $4.6B in annualized stablecoin volume on its rails and live agentic commerce in the US and CEMEA regions. Stablecoin cards are live in 50+ countries and USDC settlement is live in the US. Strategically, Visa is positioning as the bridge between traditional card infrastructure and the agent economy — keeping cards relevant by making them agent-accessible.

Notable: Visa went from publicly skeptical of crypto for years to becoming a stablecoin operator. Community commentary: "from observer to operator."

## Funding & traction

Public company. Key metrics from 2026:
- $4.6B annualized stablecoin volume on Visa rails (updated to **$7B cumulative run-rate** as of Apr 2026, expanded to 9 blockchains — per Eco/The Block)
- **17.5 billion tokens in circulation** globally — more than 3x physical cards linked to network (as of Mar 2026)
- Agentic Commerce live in US + CEMEA, now expanded to **85+ partners across Asia Pacific and Latin America** via Agentic Ready program (Apr 2026)
- USDC settlement live in the US; stablecoin settlement expanded across 9 chains (Apr 2026)
- MCP Server and Acceptance Agent Toolkit both in pilot

## Key people

No named individuals in sources.

## Products / offerings

- **Visa Intelligent Commerce** — four-service agent payment platform (tokenization, auth, controls, signals)
- **Visa MCP Server** — agent-to-API integration layer
- **Visa Acceptance Agent Toolkit** — no-code agent workflow builder
- **Visa Trusted Agent Protocol** — mentioned by Ramp as network-level agent restriction mechanism
- **Ramp Agent Cards** — single-use credentials via Visa Intelligent Commerce, locked to exact transaction at network level

## Partnerships & integrations

- [[ap2]] — AP2's Verifiable Intent is compatible with Visa's framework
- [[ramp]] — Ramp Agent Cards use Visa Intelligent Commerce
- [[mastercard]] — both networks building parallel but different approaches

## Open questions

- What is the timeline for Visa MCP Server and Toolkit to exit pilot?
- How does Visa handle dispute resolution when an agent makes an unauthorized transaction?
- Will Visa's stablecoin settlement infrastructure (USDC) become the backend for x402?
- How does Visa's card-based approach compare to [[mpp]] and [[x402]] for micropayments (<$0.01)?

## Sources

- [[visa-advances-agentic-commerce]]
- [[visa-intelligent-commerce-for-agents]]
- [[thread-fintechfrank]]
- [[visa-agentic-ready-global-expansion]]
- [[visa-token-strategy]]
- [[why-ai-agents-need-stablecoin-payments-eco]]
