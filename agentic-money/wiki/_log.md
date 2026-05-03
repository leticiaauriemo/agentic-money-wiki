# Log — Agentic Money Movement

Append-only activity record. Format: `## [YYYY-MM-DD] type | description`
Types: `ingest` | `query` | `lint` | `init`

Parse recent entries: `grep "^## \[" _log.md | tail -10`

---

## [2026-05-03] ingest | KYAPay protocol suite + Agentic Protocol Stack (kyapay.org)

Sources: `KYA.md`, `What is KYA.md`, `Buy-side roles.md`, `Sell-side roles.md`, `Infrastructure.md`, `The Agentic Protocol Stack.md` (all kyapay.org)

**New pages created:**
- [[agentic-protocol-stack-kyapay]] (summary) — three-rail taxonomy; Trust Gap analysis; AGNTCY/MCP-I; KYAPay token primitives

**Updated pages:**
- [[concepts/know-your-agent]] — major expansion: KYAPay token primitives (kya/pay/kya-pay), three buy-side identity tiers, Trust Gap (OAuth handoff problem), Relational Rail framing

**Key new concepts:**
- Three-rail taxonomy: Lightweight (x402) / High-Assurance (AP2) / Relational (KYAPay) — the "stablecoins vs. cards" framing is wrong; there are three distinct rails
- Trust Gap: no current standard for bounded agent delegation ("acting as User Y, authorized for Z only"); OAuth handoff is broken for autonomous agents
- Identity tiers: Human Principal → Agent Platform → Agent (all three must be resolved for compliant agentic transactions)
- AGNTCY (Cisco/Linux Foundation): portable "Digital Passport" for agents using W3C DIDs/VCs
- KYAPay consortium: Akamai, Experian, Consumer Reports, Forter, DataDome, Imperva, Skyfire

**x402 stats updated:** 75.41M txns/30 days (≈2.5M/day), $24.24M volume, 94K buyers, 22K sellers — significant growth from April 25 snapshot (167.96M all-time, ~200K/day)

---

## [2026-05-03] ingest | "Why AI Agents Need Stablecoin Payments" (Eco, 2026-04-30)

Source file: `Why AI Agents Need Stablecoin Payments.md` (in ` agentic-money/raw/`)
Author: Eco (eco.com) — stablecoin execution network, 15 chains.

**New pages created:**
- [[why-ai-agents-need-stablecoin-payments-eco]] (summary) — structural case; four card-rail mismatches; production evidence table; five live trade-offs; orchestration layer
- [[eco]] (company) — cross-chain stablecoin routing network; Hyperlane + CCTP

**Key new data:**
- Visa stablecoin settlement updated to **$7B cumulative run-rate** across **9 blockchains** (April 2026, The Block) — supersedes prior $4.6B figure
- Stripe x402 launch date confirmed: **February 10, 2026** (Base/USDC, Solana on roadmap)
- x402 active agents: ~**69K** (distinct from 519K wallet buyers)
- x402 average ticket: $0.31 (consistent with $0.29 dashboard figure; different snapshot dates)
- Stablecoin supply (April 29, 2026): **$318B** total — USDT $189.5B, USDC $77.3B, USDS $7.8B
- Card-rail break-even: ~$5–10 ticket; x402 average at $0.31 is well below

**Pages updated:**
- [[x402]] — added Stripe (Feb 10, 2026) and Circle as builders; confirmed 69K active agent stat; updated stat table
- [[visa]] — updated stablecoin settlement to $7B cumulative run-rate / 9 blockchains
- [[overview]] — updated volume table; added stablecoin supply note

---

## [2026-05-03] ingest | Second batch — 10 new sources → 20 pages

**Source files ingested** (from ` agentic-money/raw/` with leading space):
- `Stripe Is Trying to Make Crypto Disappear.md` (@snapcrackle, 2026-05-03)
- `AI at the Checkout > AI is the Checkout.md` (@sytaylor, 2026-05-03)
- `Giving agents the ability to pay.md` (Stripe/Dan Hill, 2026-04-29)
- `Modern banking for AI Agents.md` (meow.com/mcp, 2026-05-03)
- `Post by @0xSammy on X.md` (DripStack thread, 2026-05-01)
- `Post by @illscience on X.md` + `Post by @illscience on X 1.md` (profitable apathy; duplicates, 2026-04-27)
- `Post by @illscience on X 2.md` (agent networks open questions, 2026-05-01)
- `Post by @lightspark on X 1.md` (Grid Global Accounts, 2026-04-28)
- `Post by @lightspark on X.md` (Visa stablecoin/Bitcoin cards, 2026-04-30)

**New summary pages:**
[[stripe-is-trying-to-make-crypto-disappear]], [[ai-at-the-checkout]], [[giving-agents-the-ability-to-pay]], [[modern-banking-for-ai-agents-meow]], [[post-0xsammy-dripstack]], [[post-illscience-profitable-apathy]], [[post-illscience-agent-networks]], [[post-lightspark-grid-accounts]], [[post-lightspark-visa-cards]]

**New entity pages:**
- [[bridge]] (company) — Stripe's stablecoin orchestration + Open Issuance subsidiary; xUSD; OCC conditional trust bank charter Feb 2026; Zach Abrams CEO
- [[lightspark]] (company) — Grid platform; bounded delegation; Visa stablecoin/Bitcoin cards; MPP Bitcoin Lightning; David Marcus CEO
- [[profitable-apathy]] (concept) — consumer FS disruption thesis by Anish Acharya

**Major rewrites:**
- [[tempo]] — complete rewrite: EVM-compatible L1, Reth + Commonware, stablecoin-native gas, ISO 20022 memos, dedicated payment lanes, Tempo Zones, $5B valuation, 11 validators (Visa/Stripe/Zodia), Farcaster founders, Matt Huang triple-role CEO, Liam Horne payment channel primitive
- [[mpp]] — major expansion: 4 production features vs x402, pre-funded session model (Lightning for stablecoins), IETF submission, multi-rail at launch (stablecoin/card/Lightning), Visa card extension
- [[stripe]] — full vertical stack update: Bridge acquisition details, Privy chain-agnostic hedge, Valora team, Link 250M consumers, Issuing for agents, Link's wallet for agents, GENIUS Act positioning, Sessions 2026 signals

**Moderate updates:**
- [[universal-commerce-protocol]] — UCP Tech Council expansion (April 24, 2026); Walmart conversion data; layered architecture; merchant-owned won
- [[visa]] — anchor Tempo validator; MPP card extension; Lightspark Visa cards; x402 Foundation participation
- [[meow-technologies]] — full rail list confirmed; Grasshopper Bank N.A. (FDIC) as banking partner; MCP tool schema
- [[circle]] — First National Digital Currency Bank OCC conditional approval Dec 2025; policy vs. distribution strategy vs. Stripe

**Overview additions:** UCP Tech Council; Walmart data; profitable apathy thesis; Stripe full vertical stack; Lightspark in landscape map; Bridge in stablecoin issuance row; theses 9 and 10.

_index.md updated: 119+ pages total.

---

## [2026-04-28] ingest | "The Beginning of Agentic Finance" (Castle Labs, 2026-04-23)

Source file: `The Beginning of Agentic Finance.md` (in ` agentic-money/raw/`)
Authors: @TradFiHater and @noveleader. Comprehensive 6-chapter thesis on Ethereum as the machine economy settlement layer.

**New pages created:**
- [[the-beginning-of-agentic-finance]] (summary)
- [[erc-8183]] (concept) — commerce standard: Job primitive with escrow, delivery, evaluation; co-developed by Virtuals.io + ETH Foundation dAI team
- [[erc-8211]] (concept) — dynamic execution standard; Biconomy + ETH Foundation, April 2026
- [[crops-mandate]] (concept) — Ethereum's C/O/P/S framework for trustworthy agentic infrastructure

**Pages updated:**
- [[x402]] — added V2 features (wallet identity, modular arch, Unified Payment Interface, auto discovery), Upto scheme, speculation-correction note (~200K/day organic baseline; >50% was memecoins until Dec 2025)
- [[coinbase]] — added x402 V2 and Upto scheme; corrected transaction volume context
- [[circle]] — added Circle Nanopayments (offchain auth batching, used in OpenMind OM1 robot dog demo)

---

## [2026-04-28] ingest | "The new stack for global finance: Stablecoins edition" (a16z crypto, 2026-04-27)

Source file: `The new stack for global finance Stablecoins edition.md` (in ` agentic-money/raw/`)
Authors: Noah Levine, Guy Wuollet, Robert Hackett. a16z crypto market map of the stablecoin-powered global finance stack.

**New pages created:**
- [[the-new-stack-for-global-finance-stablecoins]] (summary)
- [[circle-arc]] (rail) — Circle's payments-specific blockchain; stablecoin-native gas, privacy, predictable costs
- [[canton]] (rail) — Digital Asset Holdings institutional blockchain for regulated entities
- [[onchain-credit-market]] (concept) — Act 2 of stablecoin economy: productive credit on programmable rails

**Pages updated:**
- [[stablecoin]] — added OCC National Trust Charter race section; added payments-specific blockchain category framework
- [[stripe]] — added Privy acquisition (alongside Bridge); added three blockchain categories context
- [[circle]] — added Circle Arc; added OCC charter race section

---

## [2026-04-27] update | Expanded stablecoin concept page

Raw source added: `stablecoin-volume-record-2025.md` (web search clipping: $33T gross volume in 2025, +72% YoY).

[[stablecoin]] concept page expanded with:
- New **Settlement speed & velocity** section: seconds/24/7 settlement; velocity doubled 2.6x→6x (a16z Q1 2026); gross vs. adjusted volume distinction (HFT/DeFi flipping effect)
- New **Volume & growth trends** section: $33T gross, C2B +128% YoY, stablecoin card collateral $300M+/month
- New **Geography** section: Asia ~2/3, North America ~1/4, Europe ~13%; BRLA ~$400M/month; counterintuitive cross-border decline (intra-country now ~75%)
- Sources updated to include [[stablecoin-volume-record-2025]] and [[9-charts-stablecoins-a16z]]

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
