---
title: "Slash"
type: company
topic: agentic-money
tags: [infrastructure, agentic-commerce, wallet, compliance, card-rails]
founded:
stage: private
hq:
sources: ["Slash for Agents — Agentic Commerce via MCP Cards Payments & Spend Controls.md"]
created: 2026-04-25
updated: 2026-04-25
---

# Slash

**One-line:** Fintech platform giving AI agents access to full card issuance, spend controls, and payment execution via MCP — with RSA-encrypted card data so agents never see raw card numbers.

## What they're building

Slash enables agents (Claude, GPT, Cursor, custom) to access its full platform via MCP without custom integration:

- **Create cards instantly** — virtual or physical, on demand
- **Enforce spend controls** — daily, monthly, lifetime limits per card or group
- **Send payments** — ACH, Slash Pay
- **Human-in-the-loop approval** — "Agent Requests": agents propose, humans approve; states: pending → approved → running → executed/rejected/expired/failed
- **RSA-OAEP encryption** — agents never see raw card numbers or CVVs; only encrypted data decryptable by user's private key
- **VGS tokenization** — raw card numbers never touch Slash servers (PCI DSS compliant)
- **Full API discovery** — agents auto-discover every Slash endpoint and inspect schemas

## Relevance to agentic money

Slash is a concrete implementation of the "scoped credentials" model for agentic payments — giving agents real spending power while enforcing hard limits at the infrastructure level (validating [[ramp]]'s research that soft guardrails fail). The RSA-OAEP encryption model is the most sophisticated card security architecture for agents described in sources.

Slash cites agentic commerce as a **$50B+ market by 2028**.

## Key stats

- 5,000+ businesses using Slash platform
- $50B+ projected agentic commerce market by 2028 (Slash estimate)

## Products / offerings

- Agentic MCP integration — full platform access for AI agents
- Virtual and physical card creation on demand
- Per-card spend controls (daily/monthly/lifetime limits)
- ACH and Slash Pay
- Agent Requests (human-in-the-loop approval workflow)
- RSA-OAEP encrypted card data
- VGS tokenization

## Partnerships & integrations

- Anthropic MCP — integration standard
- Very Good Security (VGS) — tokenization provider
- Claude, GPT, Cursor — supported agent frameworks

## Open questions

- Does Slash settle on card rails (Visa/MC) or stablecoin rails?
- How does Slash's RSA model compare to [[visa]] Ramp Agent Cards for security?
- What is Slash's transaction volume from agent-initiated payments?
- Is there a plans to integrate with [[x402]] or [[mpp]] for micropayment use cases?

## Sources

- [[slash-for-agents]]
