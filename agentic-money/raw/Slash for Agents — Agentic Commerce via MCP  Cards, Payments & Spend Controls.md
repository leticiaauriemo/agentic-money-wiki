---
title: "Slash for Agents — Agentic Commerce via MCP | Cards, Payments & Spend Controls"
source: "https://www.slash.com/platform/agents"
author:
published:
created: 2026-04-25
description: "AI agents create cards, set spend controls, and send payments via MCP. RSA-encrypted card data, human-in-the-loop approval, full Slash API access. Available to all Slash users."
tags:
  - "clippings"
---
## The new standard in agentic commerce

Create cards, set spend controls, and send payments — all through your AI agent over MCP. Never log into a dashboard again.

Available to all Slash users. [Read the docs](https://docs.slash.com/docs/mcp)

## Everything your agent needs to move money

The full Slash platform — cards, payments, accounts, treasury — accessible to any MCP-compatible AI agent. Used by 5,000+ businesses.

### Create cards instantly

Agents create virtual or physical cards on demand. Set names, types, spending limits, and assign to accounts — all through a single API call.

### Enforce spend controls

Define per-card or per-group spending constraints. Agents set daily, monthly, or lifetime limits and update them as your business needs change.

### Send payments

Move money between accounts, pay invoices, or send funds via Slash Pay — all initiated by your agent, executed by the Slash platform.

### Human-in-the-loop approval

Use read-only API keys so write operations require human approval. Agents propose actions, your team approves them — AI speed with human oversight.

### RSA-encrypted card data

Agents never see raw card numbers. PAN and CVV are encrypted with your RSA public key using RSA-OAEP before they ever reach the agent.

### Full API discovery

Agents automatically discover every Slash endpoint, inspect schemas, and understand parameter types — no manual configuration required.

## Security-first by design

Prompt injection shouldn't be able to steal your credit card. Slash uses RSA-OAEP encryption so agents never see raw card details — only tokenized, encrypted data that only you can decrypt.

### RSA-OAEP encryption

Card PAN and CVV are encrypted with your RSA public key before reaching the agent. Only your private key — which never leaves your infrastructure — can decrypt them.

### VGS tokenization

All card data is stored as VGS (Very Good Security) tokens. Even without RSA encryption, raw card numbers never touch Slash servers. PCI DSS compliant.

### Human-in-the-loop approval

Read-only API keys defer write operations for human approval. Agents propose, humans approve — with full audit trails and status tracking.

## Connect in seconds

One URL. That's all your agent needs. Point any MCP-compatible client at the Slash MCP server and start building.

```
{
  "mcpServers": {
    "slash": {
      "url": "https://mcp.slash.com/mcp?apiKey=YOUR_API_KEY"
    }
  }
}
```

## Apply in less than 10 minutes today

Join the 5,000+ businesses already using Slash.

## Frequently asked questions

Everything you need to know about agentic commerce and Slash for Agents. [Contact us](https://www.slash.com/sales-inquiry) for anything else.

What is agentic commerce?

Agentic commerce is the ability for AI agents to autonomously perform financial actions — creating cards, setting spend limits, sending payments, and purchasing goods — on behalf of a business. According to recent industry research, agentic commerce is projected to be a $50B+ market by 2028. Slash for Agents makes this possible through the Model Context Protocol (MCP), an open standard for AI-to-tool communication.

How does Slash for Agents work?

Slash provides an MCP server at mcp.slash.com that lets any AI agent interact with the full Slash API. Agents use three core tools: list\_endpoints to discover available APIs, get\_endpoint\_schema to inspect parameters and types, and call\_api\_endpoint to execute actions like creating cards, sending payments, or checking balances. The server uses standard HTTP transport and requires only an API key to connect.

Is it safe to give an AI agent access to my financial accounts?

Yes. Slash implements multiple layers of security. First, RSA-OAEP encryption ensures agents never see raw card numbers or CVVs — only encrypted data that only your private key can decrypt. Second, read-only API keys enable human-in-the-loop approval where write operations create pending Agent Requests that must be approved before executing. Third, all card data is tokenized through VGS (Very Good Security) so plaintext card numbers never touch any server. Every action is logged and fully auditable.

What is the Model Context Protocol (MCP)?

MCP is an open standard created by Anthropic that lets AI agents interact with external tools and APIs through a standardized interface. Slash implements MCP so any compatible AI agent — Claude, GPT, Cursor, or custom agents — can securely access Slash banking, cards, and payments capabilities without custom integration work.

What can an AI agent do with Slash?

Agents can access the full Slash API: create virtual and physical cards, set and update spending limits per card or card group, send payments via ACH or Slash Pay, manage invoices (create, update, reconcile), approve expense reports, query transaction history and aggregations, check account balances, manage virtual accounts, and more. The MCP server automatically discovers all available endpoints.

What are Agent Requests and how does human-in-the-loop approval work?

Agent Requests enable human oversight for AI-initiated financial actions. When an agent uses a read-only API key, write operations (like creating a card or sending a payment) return a 403 status with an approval URL instead of executing immediately. A team member reviews the proposed action in the Slash dashboard and approves or rejects it. Once approved, the original request executes automatically. Status values include pending, approved, running, executed, rejected, expired, and failed.

How do I get started with Slash for Agents?

Get your Slash API key from the dashboard under Settings, then point any MCP client at mcp.slash.com/mcp with your key. For encrypted card data, generate an RSA key pair and pass the public key as a connection parameter. Full setup instructions and decryption examples for bash, Python, and Node.js are available at docs.slash.com/docs/mcp.

Which AI agents and platforms are compatible?

Any agent that supports the Model Context Protocol — including Claude Desktop, Cursor, GPT-based agents, and custom-built agents. The MCP server uses streamable HTTP transport with JSON responses, so any HTTP-capable client can connect. No special SDK or library is required.