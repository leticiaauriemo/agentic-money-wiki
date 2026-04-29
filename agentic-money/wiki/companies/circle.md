---
title: "Circle"
type: company
topic: agentic-money
tags: [stablecoin, infrastructure, compliance]
founded: 2013
stage: public
hq: Boston, MA
sources: [Should we give AI a bank account?.md, Stablecoins Were Just the Beginning.md]
created: 2026-04-25
updated: 2026-04-28
---

# Circle

**One-line:** The issuer of USDC — the dominant stablecoin for agentic payments, processing $10 trillion in volume — co-founded by Sean Neville (now at [[catena-labs]]) and Jeremy Allaire.

## What they're building

Circle issues and manages **USDC**, the primary stablecoin used across [[x402]], [[mpp]], [[ap2]], and most agentic payment rails. Circle's role in the agentic economy is infrastructural: they don't build agent tools, but every agent that pays with USDC (the vast majority) is using Circle's reserves and minting infrastructure.

Circle operates on a **mint-and-burn** model: fiat deposited → USDC minted on-chain; USDC redeemed → fiat returned from reserves (held in cash and short-term US Treasuries). Reserve attestations published periodically.

CENTRE Consortium (governance body, co-founded with Coinbase) closed in 2023 — governance moved fully in-house.

## Relevance to agentic money

USDC is the de facto currency of the agentic internet. x402 uses USDC by default. MPP uses USDC on Tempo. AP2's crypto extension uses USDC. Without Circle's reserve infrastructure, the stablecoin layer that all agentic protocols depend on doesn't function.

The "singleness of money" problem identified by Sean Neville: a world with 10,000 stablecoins breaks because a dollar must equal a dollar everywhere. USDC's liquidity moat is what makes it the default.

## Funding & traction

- Public company (listed 2025)
- **$76 billion USDC** in circulation (as of early 2026)
- **$10 trillion** in payment volume processed via USDC
- Valued at ~**$13 billion**
- Operating for 13+ years (founded 2013)
- GENIUS Act: 7-year legislative effort completed; encodes conservative reserve requirements (T-bills, cash, highly liquid instruments) that USDC already meets

## Key people

- Jeremy Allaire — co-founder, CEO
- Sean Neville — co-founder (departed, now founder of [[catena-labs]])

## Products / offerings

- **USDC** — primary USD-pegged stablecoin; ~$76B market cap
- Reserve management — T-bills and cash backing at licensed financial institutions
- Stablecoin issuance infrastructure — global fiat on/off ramps
- **Circle Arc** ([[circle-arc]]) — Circle's purpose-built payments blockchain; stablecoin-native gas fees, privacy guarantees, predictable transaction costs; competing with Stripe's [[tempo]] in the payments-specific blockchain category
- **Circle Nanopayments** — batches thousands of offchain authorizations into single onchain settlements; used in the OpenMind OM1 robot dog electricity payment demo (first working full-stack agentic commerce loop)

## Partnerships & integrations

- [[coinbase]] — USDC co-founder; first USDC distribution partner
- [[x402]] — USDC is x402's default payment token
- [[mpp]] — USDC on Tempo is MPP's primary stablecoin
- [[catena-labs]] — Sean Neville's next company, building for agent-native banking

## OCC National Trust Charter race

Post-GENIUS Act, stablecoin issuers are racing for an **OCC National Trust Charter**. Immediate benefit is regulatory legitimacy; longer-term stakes are higher: if the OCC eventually extends charter holders **direct access to Federal Reserve rails**, the first movers become integrated into the core payment hierarchy — potential to become foundational to credit and capital markets at scale. Circle's USDC compliance positioning (T-bills/cash reserves, regular attestations) makes it one of the strongest charter candidates. — *[[the-new-stack-for-global-finance-stablecoins]]*

## Open questions

- Will Circle obtain an OCC National Trust Charter, and on what timeline?
- Does OCC Fed Reserve access materially change Circle's competitive position vs. Tether?
- How does Circle Arc differentiate from Tempo beyond the Circle brand?
- Will Circle maintain USDC dominance as other stablecoins (USDT, PYUSD, USDS) compete?
- How does the interest income model evolve if interest rates decline?

## Sources

- [[should-we-give-ai-a-bank-account]]
- [[stablecoins-were-just-beginning]]
- [[the-new-stack-for-global-finance-stablecoins]]
- [[the-beginning-of-agentic-finance]]
