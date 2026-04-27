---
title: "Post by @ExaAILabs on X — Native x402 Web Search"
type: summary
topic: agentic-money
source_type: social
tags: [infrastructure, agentic-commerce]
sources: ["Post by @ExaAILabs on X.md"]
created: 2026-04-26
updated: 2026-04-26
---

# Post by @ExaAILabs on X — Native x402 Web Search

**Source:** @ExaAILabs on X, 2026-04-07
**URL:** https://x.com/ExaAILabs/status/2041562072027427265

Announcement of Exa's native x402 integration — the first major AI research/search tool to go first-party with x402.

## The announcement

Exa (popular AI web search and research tool) partnered with [[coinbase]] to enable agents to natively pay for web search via x402.

**How it works:**
- An Exa API request made without an API key now returns an HTTP 402 status code
- The 402 response includes payment information the agent can act on
- The agent pays in USDC using proof-of-payment
- Access is granted upon successful payment verification

**Docs:** exa.ai/docs/reference/x402-guide

## Significance

Exa cited **Linux Foundation governance of x402** as the explicit reason for choosing x402 over a proprietary route. This makes Exa one of the first providers to:
1. Go first-party (not a third-party unauthorized wrapper) on x402
2. Publicly justify the choice on governance grounds

This is the "clean model" case cited in [[who-authorized-this-x402]] and [[post-bankless-x]] as the direction x402 needs to move: native integration rather than unauthorized wrappers.

## Related pages

- [[x402]]
- [[coinbase]]
- [[who-authorized-this-x402]]
- [[post-bankless-x]]
- [[introducing-agentic-market]]
