---
title: "Coinbase"
type: company
topic: agentic-money
tags: [infrastructure, stablecoin, crypto-l2, wallet, agentic-commerce]
founded: 2012
stage: public
hq: San Francisco, CA
sources: ["Welcome to x402.md, x402 - Payment Required.md", "Understanding x402 and MPP in One Article Two Routes for Agent Payments.md", "Announcing Agent Payments Protocol (AP2) Google Cloud Blog.md"]
created: 2026-04-25
updated: 2026-04-25
---

# Coinbase

**One-line:** Creator of x402, operator of the Coinbase Developer Platform facilitator service, and co-founder of the x402 Foundation — positioning as the infrastructure layer for all AI agent payments on open blockchain rails.

## What they're building

Coinbase's agentic payments strategy centers on three products:

**1. x402 Protocol** — the open HTTP-native payment standard built on Base (and other chains). Coinbase authored the whitepaper (May 2025), runs the facilitator service, and co-founded the x402 Foundation with Cloudflare. License: Apache 2.0.

**2. Coinbase Developer Platform (CDP) Facilitator** — processes ERC-20 payments on Base, Polygon, Arbitrum, World, and Solana. Free tier: 1,000 transactions/month; $0.001/transaction thereafter. Enables agents to pay without running their own on-chain infrastructure.

**3. AgentKit / Agentic Wallet** — wallet tooling enabling agents to hold and spend stablecoins programmatically. Integrated with LangChain, CrewAI, and other agent frameworks.

## Relevance to agentic money

Coinbase wrote the x402 whitepaper, operates the primary facilitator, and has 167.96M+ transactions through the ecosystem (as of April 2026). They're the picks-and-shovels play: whether merchants use x402 directly or through an abstraction, Coinbase is often settling the transaction on Base.

Quoted by Erik Reppel (Head of Engineering, CDP) in the AP2 announcement: "With x402 and AP2, agent-to-agent payments are becoming mainstream."

## Key stats

- x402 all-time transactions: **167.96M** (April 2026)
- x402 all-time volume: **$49.51M**
- x402 buyers: **519.45K**
- x402 sellers: **99K**
- CDP facilitator: 1,000 free txns/month, $0.001/txn after
- Claimed 50M+ transactions through Agentic Wallet infrastructure (note: may include test transactions)

## Key people

- Erik Reppel — Head of Engineering, Coinbase Developer Platform
- Jesse Pollak — creator of Base, prominent on agent payments (source to be ingested)

## Products / offerings

- **x402** — HTTP-native payment protocol (open source, coinbase/x402 on GitHub)
- **CDP Facilitator** — managed payment processing on Base/Polygon/Arbitrum/World/Solana
- **AgentKit** — agent wallet and payment tooling
- **Agentic Wallet** — wallet infrastructure for agents
- **Base** — L2 blockchain (primary settlement layer for x402)
- **USDC** — stablecoin (co-issued with Circle, primary x402 currency)

## Partnerships & integrations

- [[ap2]] — Erik Reppel quoted as AP2 launch partner; x402 is the crypto extension for AP2
- [[x402]] — creator and foundation co-founder
- Cloudflare — x402 Foundation co-founder
- Stellar, Solana, World — chains supported via CDP facilitator
- Google, AWS, Anthropic — all integrated x402 into their agent platforms
- Lowe's Innovation Labs — retail x402 demo

## Open questions

- How does Coinbase monetize x402 beyond the CDP facilitator $0.001/txn fee?
- Does Coinbase want x402 to remain open, or will CDP become a walled garden over time?
- What is the split between "real" economic activity and testing/gaming in the 167.96M transactions?
- How does USDC issuance revenue compound with x402 volume?

## Sources

- [[welcome-to-x402]]
- [[x402-payment-required]]
- [[understanding-x402-and-mpp]]
- [[announcing-ap2-google-cloud]]
