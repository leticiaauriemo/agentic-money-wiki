# Log — Agentic Money Movement

Append-only activity record. Format: `## [YYYY-MM-DD] type | description`
Types: `ingest` | `query` | `lint` | `init`

Parse recent entries: `grep "^## \[" _log.md | tail -10`

---

## [2026-04-26] ingest | Batch 3 — 15 new sources → 20 pages

Summary pages created: [[who-authorized-this-x402]], [[post-bankless-x]], [[introducing-agentic-market]], [[post-exa-ai-labs-x]], [[erc-8004-trustless-agents]], [[near-intents]], [[openclaw-product]], [[9-charts-stablecoins-a16z]], [[get-started-with-bvnk]], [[enterprise-stablecoin-payments-bvnk]], [[agent-ready-paypal]], [[agentic-commerce-services-paypal]], [[agentic-commerce-solutions-paypal]], [[payments-for-ai-agents-natural]], [[agentic-payments-memo-natural]]

Entity pages created: [[natural]] (company), [[bvnk]] (company), [[near]] (company), [[peter-steinberger]] (player), [[x402-governance]] (concept)

Key new findings:
- **x402 governance crisis**: unauthorized wrappers of Wolfram Alpha, Amadeus, Google Flights on Agentic.Market; no provenance layer; Google Flights removed 2026-04-25; Exa goes first-party citing Linux Foundation governance
- **PayPal full strategy**: Store Sync (catalog syndication via Cymbio/Wix/BigCommerce) + Agent Ready (OpenAI ACP, one-time-use Braintree nonces); confirmed live partners: Perplexity, Google
- **Natural seed memo** (Kahlil Lalji): A2A/A2B/A2C taxonomy; 5 structural problems (slow rails, dispute ambiguity, identity, global payments, fraud controls break); 6 products; PayPal-esque distribution strategy
- **ERC-8004**: three-registry standard (Identity/ERC-721, Reputation, Validation) by MetaMask + Ethereum Foundation + Google + Coinbase; the on-chain KYA standard
- **a16z stablecoin data** (Q1 2026): ~$4.5T adjusted volume; C2B +128% YoY; velocity 2.6x→6x; cross-border share DECLINING (intra-country now ~75%); Asia dominates (~2/3)
- **NEAR Intents**: $17B+ volume, 31 chains, 125+ assets; designed for AI agents
- **OpenClaw**: Peter Steinberger's viral open-source personal agent (Jan 2026); creator joined OpenAI Feb 15, 2026

Raw files sourced: `Who Authorized This? The Gray Area of x402.md`, `Get started with BVNK.md`, `Introducing Agentic.Market The Homepage of the Agent Economy.md`, `OpenClaw — Personal AI Assistant.md`, `Payments for AI agents.md`, `Post by @ExaAILabs on X.md`, `ERC-8004 Trustless Agents.md`, `Enterprise Stablecoin Payments Infrastructure.md`, `Post by @Bankless on X.md`, `Agent Ready.md`, `NEAR Intents - The Universal Liquidity Protocol.md`, `Agentic commerce services.md`, `Agentic payments memo.md`, `9 charts on what stablecoins are becoming.md`, `Agentic Commerce Solutions for Businesses.md`

_index.md updated: 95+ pages total.

## [2026-04-26] ingest | New sources: IMF Note 2026/004 + x402 whitepaper PDF

Pages created: [[imf-agentic-ai-payments]] (summary), [[x402-whitepaper-technical]] (technical spec), [[paypal]] (company), [[universal-commerce-protocol]] (concept).

Key new findings: IMF's three-layer framework (intent → authorization → settlement); Google UCP (Jan 2026); PayPal Cymbio acquisition; Amazon "Buy for Me"; OpenAI/Stripe 4% fee on agent-led conversions; Gartner 80% customer service resolution by 2029; 10-category risk classification matrix; Kill switch recommendations.

## [2026-04-26] ingest | Full batch ingestion — 52 sources → 70+ pages

Full ingestion of all sources in `raw/`. All summaries, entity pages, and concept pages created or updated.

**Rails & protocols:**
[[x402]], [[mpp]], [[ap2]] — created in prior session; stats updated.

**Company pages created/confirmed:**
[[brex]], [[catena-labs]], [[circle]], [[coinbase]], [[era]], [[jpmorgan]], [[mastercard]], [[meow-technologies]], [[merit-systems]], [[ramp]], [[slash]], [[stripe]], [[sui]], [[tempo]], [[visa]]

**Concept pages created/confirmed:**
[[agentic-banking]], [[agentic-commerce]], [[bank-readiness-agentic-payments]], [[headless-merchants]], [[know-your-agent]], [[session-payments]], [[stablecoin]]

**Summary pages created (protocols & infrastructure):**
[[x402-whitepaper-summary]], [[welcome-to-x402]], [[x402-ecosystem-explorer]], [[understanding-x402-and-mpp]], [[announcing-ap2-google-cloud]], [[introducing-the-machine-payments-protocol]], [[agentic-payments-tempo]], [[what-are-stablecoins-tempo-1]], [[one-balance-agentcash]], [[marketplace-x402scan]], [[x402-agentic-commerce-aws]], [[missing-infrastructure-ai-agents-a16z]]

**Summary pages created (card networks & banks):**
[[santander-mastercard-europe-first-ai-payment]], [[mastercard-advances-agentic-payments-latin-america]], [[mastercard-goes-live-singapore-malaysia]], [[visa-advances-agentic-commerce]], [[visa-intelligent-commerce-for-agents]], [[jpmorgan-citi-payments-frontier]]

**Summary pages created (fintech products):**
[[meow-technologies-agentic-banking-launch]], [[agents-on-brex]], [[catena-labs-website]], [[an-ai-agent-with-a-wallet]], [[make-claude-manage-money]], [[should-we-give-ai-a-bank-account]], [[banks-shift-ai-chatbots-autonomous]], [[sui-agentic-finance]], [[jesse-pollak-agents-crypto-payments]]

**Summary pages created (analysis & research):**
[[three-gaps-agentic-payments]], [[coding-agents-ignore-budgets]], [[machine-economy-2030]], [[agentic-economy-massive-commerce-wont]], [[agentic-commerce-wont-kill-cards]], [[agentic-payments-buzz-real-gap]], [[agentic-payments-are-coming-srm]], [[agentic-payments-use-cases-ramp]], [[is-2026-year-agentic-payments]], [[stablecoins-were-just-beginning]], [[earning-consumer-trust-summary]], [[as-fraud-agentic-risks-mount]], [[post-victor-yaromin-linkedin]]

**Summary pages created (banking & industry reports):**
[[agentic-ai-banking-blueprint]], [[agentic-ai-payments-regulatory-frameworks]], [[agentic-banking-how-ai-agents-transform-finance]], [[agentic-banking-when-money-thinks]], [[agentic-commerce-future-shopping-jpmorgan]], [[ritual-whitepaper-summary]]

**Summary pages created (social posts & threads):**
[[thread-a16z]], [[thread-fintechfrank]], [[post-0xcygaar]], [[post-merit-systems-x]]

**Files not ingested (unreadable content):**
- `Artemis Agentic Commerce Landscape.md` — corrupted (only navigation/metadata elements captured from web clipper)
- `Open Agentic Commerce.md` — empty (web clipper captured no content)

**Infrastructure fixes applied:**
- Fixed triple-nested `raw/raw/raw/` directory structure → flattened to `raw/`
- Extracted 3 PDFs using `pypdf` → `.txt` files (earning-consumer-trust, Ritual-WP, and one other)

**Overview updated:** Yes — full rewrite to reflect ~52 sources.

---

## [2026-04-25] ingest | "Three Gaps" (Forbes / Dimitar Dimitrov, 2026-04-21)

Pages created: [[three-gaps-agentic-payments]] (summary), [[bank-readiness-agentic-payments]] (concept), [[dimitar-dimitrov]] (player).

## [2026-04-25] ingest | "What are stablecoins?" (Tempo docs, 2026-01-29)

Pages created: [[what-are-stablecoins-tempo-1]] (summary), [[stablecoin]] (concept), [[tempo]] (company). Updated [[mpp]] to link Tempo properly.

## [2026-04-25] init | Rails pages created: x402, MPP, AP2

Created rail pages for the three main agentic payment protocols from live research (no raw/ source files yet — stats sourced from x402 ecosystem dashboard, MPPscan, and web search). Stats will need periodic refresh.

## [2026-04-20] init | Wiki created

Wiki scaffolded for topic: agentic money movement.
Entity types defined: companies, concepts, rails, use-cases, players.
Seeded open questions in CLAUDE.md.
Ready for first source ingestion.
