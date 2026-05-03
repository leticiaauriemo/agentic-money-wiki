---
title: "Visa Intelligent Commerce for Agents"
type: summary
topic: agentic-money
source_type: company-blog
tags: [card-rails, agentic-commerce, infrastructure, identity-kyc]
sources: [Visa Intelligent Commerce for Agents.md]
created: 2026-04-25
updated: 2026-04-25
---

# Visa Intelligent Commerce for Agents

**Source:** [Visa Developer Portal](https://developer.visa.com/use-cases/visa-intelligent-commerce-for-agents)

## What it is

Visa Intelligent Commerce is Visa's platform for AI agent-initiated payments. Four integrated services enable agents to make secure, seamless purchases on behalf of users.

## Four services

1. **Tokenized credentials** — agent-specific tokens bound to context; usable only by that agent on that user's behalf
2. **Authentication** — cardholder verifies once; token carries forward
3. **Payment controls** — limits and restrictions aligned with user intent and scope
4. **Commerce signals** — transaction tracking and dispute management

## Current status

"In the process of development and deployment" — not yet fully live as of April 2026.

## Design principles

- Agent cannot exceed user-defined scope
- Credentials are agent-specific (not shared credentials)
- Framework supports discovery, personalization, and payment

## Relationship to Visa MCP Server

The developer documentation (separate source) reveals the MCP server is the integration layer on top of this credential/authentication/controls framework. Developers access these four services through the MCP interface.

## Related pages

- [[visa]]
- [[visa-advances-agentic-commerce]]
- [[know-your-agent]]
- [[agentic-commerce]]
