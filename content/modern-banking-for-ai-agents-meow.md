---
title: "Modern Banking for AI Agents (Meow MCP)"
type: summary
topic: agentic-money
source_type: company-blog
tags: [infrastructure, bank-api, wallet, agentic-commerce]
sources: [Modern banking for AI Agents.md]
created: 2026-05-03
updated: 2026-05-03
---

# Modern Banking for AI Agents (Meow MCP)

**Source:** [meow.com/mcp](https://www.meow.com/mcp), captured 2026-05-03
**Banking services provided by:** Grasshopper Bank, N.A.; Member FDIC

## What it is

Meow's MCP integration lets AI agents (Claude, ChatGPT, Gemini, Grok) interact with a full suite of business banking services through a single API. "One API. Every way to move money."

**Supported rails:**
| Rail | Networks |
|------|---------|
| ACH | Domestic |
| Wire Transfer | Domestic |
| USDC | Ethereum, Base, Solana, Arbitrum |
| USDT | Ethereum |
| International Wire | Cross-border |
| Book Transfer | Internal |
| Card Payments | Corporate cards |

This answers the previously open question of which bank partner Meow uses: **Grasshopper Bank, N.A.** (Member FDIC).

---

## Demo capabilities

Every example below is a real MCP interaction. Key MCP tools used in each:

| Task | Tools called |
|------|-------------|
| Morning cash briefing | `get_account_balances`, `list_bank_accounts` |
| Transaction review | `list_account_transactions` |
| Burn rate analysis | `get_account_balances` (time-series) |
| Routing number validation | `validate_routing_number` |
| Payment rail discovery | `list_account_payment_networks` |
| Crypto invoice discovery | `list_invoices`, `list_invoicing_customers` |

**Routing validation example:** Agent confirms that routing number 021000021 is JPMorgan Chase Bank, NA (New York, NY), supports both Wire and ACH — before initiating a transfer.

**Crypto invoicing:** Meow invoices automatically provide USDC wallet addresses across chains (ETH, Base, Solana) when crypto payment is enabled.

---

## Agent onboarding flow

Designed so an AI agent handles the onboarding itself via a single CLI command or a copy-pasted prompt. Supported by: Claude Code, Cursor, Windsurf, Codex, Claude Desktop.

The docs live at `meow.com/skills.md` — a machine-readable endpoint that agents can read directly to set themselves up.

---

## What this adds to the wiki

This source confirms several previously open questions about Meow Technologies:
- **Banking partner:** Grasshopper Bank, N.A. (FDIC insured)
- **Full rail list:** ACH, Wire, International Wire, Book Transfer, Card, USDC (4 chains), USDT (Ethereum) — broader than originally noted
- **Crypto invoicing:** Agents can query which invoices accept crypto and retrieve wallet addresses
- **MCP tool schema:** Confirms named tools (`list_account_payment_networks`, `validate_routing_number`, etc.)

---

## Related pages

- [[meow-technologies]] — main company page
- [[mpp]] — machine payment protocol
- [[x402]] — competing micropayment protocol
