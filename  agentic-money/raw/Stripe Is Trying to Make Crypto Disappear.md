---
title: "Stripe Is Trying to Make Crypto Disappear"
source: "https://x.com/snapcrackle/status/2050910293597856077?s=46"
author:
  - "[[@snapcrackle]]"
published: 2026-05-03
created: 2026-05-03
description: "After the Tether Deep Dive, I became interested in how larger organizations approach their crypto strategy. So I went down the Stripe rabbit..."
tags:
  - "clippings"
---
![Image](https://pbs.twimg.com/media/HHDrh4xXYAAQtFL?format=jpg&name=large)

After the [Tether Deep](https://news.enterpriseonchain.com/p/tether-is-not-a-stablecoin-company?utm_source=news.enterpriseonchain.com&utm_medium=newsletter&utm_campaign=stripe-is-trying-to-make-crypto-disappear&_bhlid=71cd4a8d962252c505ac9e52ed808ad418bc780e) [Dive](https://news.enterpriseonchain.com/p/tether-is-not-a-stablecoin-company?utm_source=news.enterpriseonchain.com&utm_medium=newsletter&utm_campaign=stripe-is-trying-to-make-crypto-disappear&_bhlid=d605aacd83914467cbcdd4a9c6e0983c6d3c2ae8), I became interested in how larger organizations approach their crypto strategy. So I went down the Stripe rabbit hole, and I realized they have a whole stack being built out.

Most people are still asking whether Stripe is becoming a crypto company. I think that's backwards.

Stripe is trying to make crypto disappear. Not in a negative way, but by burying it so far inside enterprise payment infrastructure that the customer never has to say wallet, gas, bridge, validator, or chain. The stablecoin is there. The blockchain is there as plumbing.

Over the last eighteen months, Stripe has acquired Bridge (stablecoin orchestration and issuance, $1.1 billion, October 2024), Privy (wallet infrastructure, June 2025), and the Valora team (the engineers behind cLabs's mobile stablecoin app, December 2025; the app and IP returned to cLabs). It has co-founded (or incubated, depending on who you talk to) Tempo, a purpose-built payments blockchain that went live on mainnet in March 2026 at a $5 billion Series A valuation. Its stablecoin subsidiary received conditional OCC approval for a national trust bank charter in February 2026.

The architecture is a payments company that has absorbed a stablecoin orchestrator, a wallet infrastructure company, a mobile payments team, and a Delaware-incorporated layer-one network.

That's the company. The more interesting thing, which I'll get to, is that Circle independently arrived at almost exactly the same architecture with Arc.

**What Stripe Assembled**

The easiest way to see Stripe's position is to go over the stack.

At the settlement layer sits Tempo. Built jointly with Paradigm, incubated inside a Delaware C-corp called Tempo Labs (filed May 2025, three months before Matt Huang's CEO appointment was announced). EVM-compatible, running Paradigm's Reth execution client and a consensus library called Commonware built by Patrick O'Grady's team. Stablecoin-native gas (no native token). Dedicated payment lanes. Memos aligned to ISO 20022. Careful design choices are being made here.

At the orchestration and issuance layer sits Bridge. Founded in 2022 by Zach Abrams (ex-Coinbase, ex-Brex CPO) and Sean Yu. Acquired by Stripe in October 2024 for $1.1 billion, the largest crypto M&A deal on record at the time, since surpassed by Mastercard's acquisition of BVNK for up to $1.8 billion in March 2026. Bridge's Open Issuance platform, launched September 2025, is where Phantom, Klarna, Hyperliquid, and MetaMask have all spun up their own stablecoins. Bridge handles reserves, compliance, mint and burn. Issuers keep the majority of the reserve yield.

The Open Issuance economics are interesting. By sharing the majority of reserve yield with each issuer rather than absorbing it, Bridge turns reserve income into the stablecoin equivalent of app-store economics. Stripe doesn't need to own every branded coin if it owns the platform where coins are launched, custodied, swapped, reconciled, and regulated. They are building a different kind of moat than processing fees. It's a take rate on the float, paid in exchange for handling the parts issuers don't want to manage (compliance, reserve management, banking relationships, regulatory navigation). John Collison made an observation at Sessions 2025. Bridge's first-year payment volume was on a steeper exponential than Stripe's own first two years of existence. However, I think the chart isn't only about Bridge's growth. It's about Stripe's distribution. Bridge inside Stripe gets momentum, no standalone stablecoin orchestrator has, and the same compounding distribution effect is what Privy, Tempo, and the trust charter benefit from once they are plumbed into the platform. A year on, we can see what compounded.

At the wallet layer sits Privy. Founded by Henri Stern and Asta Li in 2021. Acquired June 2025 at undisclosed terms (its last private valuation was reportedly around $230 million). By the time of Stripe's 2025 annual letter, it had 110 million programmable wallets. Secure enclaves plus Shamir's Secret Sharing, which means neither the application nor Privy holds the full key. Privy has continued to behave as if neutrality matters. Whether by explicit acquisition condition or commercial necessity, it appears it has remained chain-agnostic rather than becoming a pure Tempo feeder.

That neutrality already produced something Stripe probably didn't predict at the time of acquisition. In September 2025, Privy partnered with AllUnity to power EURAU, the first euro stablecoin licensed as electronic money under German BaFin. EURAU is not a Bridge product. It is, in effect, a competing euro stablecoin to anything Bridge might eventually issue through Open Issuance. And Privy is powering it.

This tells me Privy is Stripe's insurance policy, not just its wallet layer.

If Bridge's trust charter hits friction, or if Open Issuance's yield-sharing model runs into the OCC rulemaking I'll get to shortly, Privy keeps running as a chain-agnostic embedded-finance layer that sits across any issuer and any chain. Bridge is the bet. Privy is the hedge. The undisclosed acquisition price at my guess, is Stripe paying for optionality.

Privy handles the developer and embedded wallet side. The consumer side has its own wallet layer too. Link, Stripe's accelerated checkout product, now holds stablecoins for 250 million consumers, announced at Sessions 2026. When Meta sends stablecoin payouts to creators in the Philippines or Colombia via Stripe, the creators receive them inside Link. They sign in with email, see a balance, and never see a wallet, address, or chain. The make-crypto-disappear thesis runs both sides. Merchants see Stripe Balance. Consumers see Link.

At the fiat-rail layer sits Stripe itself. $1.9 trillion in payment volume in 2025, up 34% year-on-year. 5 million businesses. 99.999% uptime. 195 countries.

And sitting across the top of all of this is Bridge's pending OCC national trust bank charter, conditionally approved in February 2026. The conditions: $45 million of Tier 1 capital, plus eligible liquid assets equal to the greater of 50% of Tier 1 capital or $27.5 million for the first three years of operation, capital raised within twelve months, bank open within eighteen, charter limited to trust activities. The OCC filing also says explicitly what the bank intends to do once open: issue stablecoins, serve as primary issuer of xUSD, provide custody, and support both affiliates and unaffiliated institutional customers.

That last clause is the part most coverage missed. Bridge isn't applying for a trust charter to hold Stripe's own reserves. It's applying to be the bank that other people custody through.

Michael Lempres, formerly Coinbase's Chief Legal and Risk Officer, is one of the named organisers. Before Coinbase he was an Assistant Secretary of Defense and Chief of Staff at Treasury. You don't hire a CV like that to run a $45 million entity that just sits there. That's a platform build. **My prediction: within eighteen months of final approval, Bridge applies for expanded OCC authorities to custody stablecoin reserves for third-party fintechs.** The OCC filing already positions this as the move to make.

A national trust charter does not make Stripe a bank holding company under the Bank Holding Company Act. That structural detail is the whole point. Stripe gets federal regulatory legitimacy without becoming bank-regulated.

Nobody else owns quite this combination. Circle has USDC, Arc, CPN, policy credibility, and now its own conditional national trust bank path through First National Digital Currency Bank (OCC conditional approval, December 2025). Coinbase has custody, Base, and x402. Visa has rails and stablecoin card programmes. Mastercard has its Multi-Token Network and BVNK. Stripe's difference is that it combines merchant distribution at $1.9 trillion of payments volume, embedded wallets via Privy, stablecoin issuance infrastructure via Bridge, settlement-chain ambition via Tempo, an HTTP machine-payment standard via MPP, and a federal trust-bank path via Bridge National Trust Bank, all inside one orbit.

## Why Tempo Exists

Buried in Stripe's 2025 annual letter is a paragraph that tells you more about the strategic reasoning than any press release. During a memecoin trading frenzy on one of the major blockchains, a Bridge customer waited more than twelve hours for a payout to clear. Per-transaction prices spiked 35x in the same window.

I think this is the event that crystallized the Tempo decision internally. You cannot run institutional payment flows on infrastructure that occasionally becomes unreachable because a social-media coin is having a moment. If your business is moving money at scale for regulated counterparties, you need a settlement layer with predictable performance, predictable fees, and no shared blockspace with speculative activity.

Stripe had three options. Build on Ethereum (congestion risk, shared blockspace, fee unpredictability I assume were major concerns for payments). Build on a high-throughput public chain like Solana, and accept that consumer speculation can still leak into enterprise settlement. Or build something purpose-built.

They picked the third, and they did it in partnership with Paradigm rather than alone. That matters. Matt Huang runs Tempo as CEO, manages Paradigm, and sits on Stripe's board. This is a structure institutions will want to understand.

![Image](https://pbs.twimg.com/media/HHDy15faYAAYtP0?format=jpg&name=large)

The technical design is payments-first in a way that reads as novel to me (I don't get to use that word often). No native token, so no separate asset to acquire before you can use the chain. Stablecoin-native gas, so fees are paid in the same unit of account as the payment itself. Dedicated blockspace lanes that reserve capacity for payments and prevent the memecoin-congestion scenario from repeating. ISO 20022-aligned memos for ERP reconciliation. Optional privacy with compliance blocklists. A Fee AMM that auto-converts stablecoin gas to the validator's preferred stablecoin.

This is not a chain for decentralized social networks or experimental DeFi. It is a chain for settling B2B payments, cross-border remittances, payroll, and machine payments. The audience is the treasury function at a Fortune 500 company, not a crypto-native user holding their own keys - and it’s not pretending to be anything but that.

## What the Public Chain Actually Looks Like

As of mid-April 2026, about a month after mainnet launch, Tempo had eleven validators based on the public validator set I rcould find. Most of them were operated by Tempo itself. Visa, Stripe, and Zodia Custody (Standard Chartered's majority-owned custodian) were announced as the first external validators on April 14th, 2026. There is no staking requirement. Validators do not commit capital. They are selected by a multisig controlled by the Tempo team.

Zodia is the validator worth sitting with. Standard Chartered is the UK bank with the deepest position in Hong Kong's new stablecoin licensing regime and the most institutional crypto reach across the Middle East. Zodia as anchor validator alongside Visa and Stripe is a jurisdictional tell. **Lower-confidence prediction:** the first non-US regulated stablecoin on Tempo mainnet is more likely to come through the Hong Kong / Standard Chartered corridor than the euro corridor, within the next twelve months. The euro path runs separately through Privy and AllUnity. The institutional Asia path runs through Zodia and Tempo. Two architectural bets in parallel.

This looks less like cryptoeconomic security and more like governed financial-market infrastructure. Closer to how Visa or DTCC are governed than how Ethereum is.

There's a structural reason for this that goes beyond performance. Permissioned validators are a compliance interface. A bank risk committee can underwrite Visa, Zodia, Standard Chartered, and Stripe. The permissioned design isn't only about fees and throughput. It's about institutional legibility, which is what makes the chain available to counterparties whose risk frameworks were not built to evaluate cryptoeconomic security as a primary control.

The same logic applies to the rest of the stack. For a consumer crypto user, the question is "did the transaction settle." For an enterprise, the question is different. Can my accounting, tax, treasury, compliance, sanctions, refund, chargeback, and audit systems understand what just happened. A payment that settles instantly but creates accounting ambiguity is not enterprise-grade. Stripe's advantage is that the payment can land inside the same dashboard, ledger exports, tax logic, fraud systems, and refund workflows merchants already use. Settlement is not the finish line. Reconciliation is. That's the distinction Stripe is built to win.

![Image](https://pbs.twimg.com/media/HHDyAeLbwAAsI0q?format=jpg&name=large)

On the public-chain metrics most crypto analysts look at, Tempo is very small. DeFiLlama showed about $3 million in TVL as I was writing, with effectively no fees on the public crypto side. The partner list, by contrast, is enormous. Visa as anchor validator. Standard Chartered via Zodia. Deutsche Bank running testnet workloads. OpenAI and Anthropic as design partners on the AI-agent side. A long tail of others including Mastercard, Nubank, Shopify, Klarna, Revolut, DoorDash, Fifth Third, Coastal Community Bank, plus infrastructure partners across the stack.

Crypto analysts are trained to look for TVL, fees, daily active addresses, liquidity. Tempo looks unimpressive on those metrics because those are not the metrics it is being built to win. Tempo's adoption curve is procurement-led, integration-led, compliance-led. Two things are true at once. The public metrics are tiny. The partner list is impressive. That's not a contradiction. That's the business model.

Henri Stern, who runs Privy inside Stripe's corporate family, went on John Collison's podcast in November 2025 and openly flagged the concern that Tempo could over-centralise, and that the 2-3 year journey of actually decentralising the validator set was unresolved. I watched that segment twice. It's a remarkable moment. A subsidiary CEO voicing a governance concern about the parent company's affiliated chain, on the parent company's own channel. Whatever the internal calculation that led to that being aired, it tells you the Stripe leadership are not pretending the decentralisation question is closed.

Buried in the Bankless podcast with Tempo's engineering lead after mainnet launch is a detail that does not appear in any Stripe or Paradigm press release. Tempo ships a one-way payment channel primitive at the L1 level, built on prior state-channel work, with Liam Horne on the Tempo team (the former Optimism CEO who co-founded Connext during the 2018 state-channel era). The MPP "session" mode this enables is Lightning for stablecoins, running inside Tempo itself.

What this tells me is that Tempo already knows its current architecture cannot handle agent-scale microtransactions on-chain. If AI agents are going to pay for API calls at per-inference pricing, the settlement happens off-chain and batches periodically to L1. The published throughput target of 100K+ TPS with sub-second finality is the headline. The real target is unlimited off-chain throughput batched and settled to L1 for an audit trail.

I expected Tempo to solve this with rollups or state channels announced post-mainnet. What they have already started shipping is more institutionally legible: **Tempo Zones**. EVM-compatible private chains running parallel to mainnet, designed for privacy, scalability, compliance controls, and enterprise use cases like payroll. Operators see activity inside their zone. Compliance logic can restrict transfers or withdrawals. The architecture isn't "one public chain handles everything." It's "controlled execution domains, periodic settlement, auditability, with mainnet as the public bond."

That is closer to a SWIFT-with-blockspace design than to a cryptocurrency-style settlement layer. **I think the agent-scale microtransaction layer ships under the Zones umbrella, not as a separate rollup brand.** Watch for AI-agent-focused Zones to be named, probably with OpenAI or Anthropic as the first announced operator.

## Machine Payments Protocol and the Control Plane

On the same day Tempo went live, Stripe launched the Machine Payments Protocol. MPP is an open standard for how AI agents pay for things over HTTP. It was submitted to the IETF as a proposed payment authentication scheme.

Most of the analysis of MPP has framed it as Stripe's proprietary alternative to x402, the HTTP-402-based payment protocol that Coinbase released in May 2025 and handed to a new Linux Foundation entity (the x402 Foundation) in September 2025. That framing is not quite right.

MPP and x402 share the same HTTP 402 handshake pattern. MPP adds four production features that x402 in its current form lacks: first-class idempotency, request-body digest binding, credential expiration, and structured receipts. It also adds a pre-funded session model, so an agent can deposit once and spend against balance via off-chain vouchers settled in batches. That is what makes token-streaming and per-inference AI billing economically viable. x402 in its current shipped form settles each call on-chain. MPP does not have to.

MPP is also more explicitly rail-agnostic at launch inside Stripe's commercial stack. At launch it supports stablecoin payments on Tempo, fiat methods such as cards and BNPL through Shared Payment Tokens, and Bitcoin Lightning via Lightspark. Visa has already published a card-based MPP extension. x402 began as an HTTP stablecoin-payment protocol and is being generalised by the x402 Foundation, whose participants include Adyen, AWS, American Express, Google, Mastercard, Shopify, Stripe, and Visa. The two standards may converge at the foundation layer over the next year. That convergence is what Stripe is set up to benefit from.

This is the architectural reason MPP is not a threat to Stripe's own business. The current x402 implementation runs on stablecoin chains and bypasses card networks, which means it bypasses interchange. MPP preserves the card path as an option. When an AI agent pays via MPP using a Shared Payment Token, interchange is preserved and Stripe stays in the flow. When the same agent pays via MPP using stablecoin, the settlement happens on Tempo and the flow still touches Stripe's balance sheet. Either way, Stripe does not get disintermediated.

Georgios Konstantopoulos, Tempo's engineering lead and formerly Paradigm's CTO, put it more diplomatically on the Bankless podcast. He said MPP and x402 could compete, or they could converge. I think Stripe's actual thinking is embrace and absorb. Stripe's own documentation supports both protocols. Visa has extended MPP through its Intelligent Commerce and Trusted Agent Protocol work. Cloudflare added an MPP proxy repository on launch day.

If you want the single line that captures this: Stripe doesn't care which protocol wins, it cares that settlements land in Stripe balances. The more precise version of the same point: Stripe does not need to win the protocol war. It needs the winning protocol to terminate inside Stripe's balance, compliance, and reporting layer.

Sam Altman, on stage with Patrick Collison at Sessions 2026, described OpenAI's intended business model in unusual terms. He said he would like OpenAI "to be an infrastructure provider" and to be "like a forever low margin as long as we can be huge and growing fast business." He cited Stripe explicitly as the template. The most influential AI lab in the world has publicly chosen not to compete with Stripe at the payments layer. That is a structural advantage for any payment-rail standard Stripe co-authors with the AI-side incumbents.

![Image](https://pbs.twimg.com/media/HHPPh3xWAAAxwAa?format=png&name=large)

Stripe's developer keynote at Sessions 2026 included a cool data point. In 2025, AI agent traffic to Stripe's documentation went from less than 5% to nearly 40% of total docs traffic. Stripe's documentation is now the primary reference manual the AI economy is reading from. When the agents building the agent economy are already integrating against your APIs by default, you have material advantages defining the standards.

There's a second tell in the MPP story. Dan Romero and Varun Srinivasan, the founders of Farcaster, joined Tempo in February 2026. Farcaster's founders don't join a payments blockchain for the stablecoin rails. They join because something is being built that needs social and identity primitives.

This is the most speculative prediction, so flagging it as such: I think Tempo ships an agent-identity layer within twelve months, positioned as verifiable identity for AI agents but using Farcaster-style social graph primitives adapted for machine actors. The reason this matters to institutional readers is that Ethereum has its own attempt at this called ERC-8004, currently working through the standardisation process.

Visa is already extending MPP through its Trusted Agent Protocol work, which means the agent-identity fight may not be Tempo versus Ethereum alone. It may be Tempo, Ethereum, and the card networks all trying to define what a machine actor is allowed to be. Identity is where payments attach. Whoever owns identity owns the whole flow.

## Disruption From the Inside

There's a question that existing coverage misses. Stripe's existing business runs on card interchange. Every Visa or Mastercard transaction Stripe processes generates revenue from the card networks' interchange flow.

Stablecoin payments on Tempo bypass card networks. If MPP and stablecoin settlement work as designed, agents and merchants increasingly pay each other on Tempo rails. The interchange revenue Stripe currently depends on starts being routed around.

Stripe is building the thing that, if it succeeds, hollows out the business model that funded its construction.

When an agent pays via MPP using a card token, the card flow is preserved and Stripe takes its existing fee. When the same agent pays via MPP using stablecoin, the new flow is captured by Bridge (issuance and reserves), Tempo (settlement), and the merchant's Stripe balance. Whichever rail wins, the payment ends up in a system Stripe owns. The pivot happens inside Stripe's own architecture rather than outside it. This is not most companies' instinct. Most incumbents protect the existing revenue and hope the new technology takes longer to arrive. Stripe is doing the opposite. It is building the thing that competes with its own card business on its own timeline, while ensuring the new flows route through systems Stripe also owns. What we're seeing is a willingness to keep ripping up its own rule book

## The Circle Mirror

Jeremy Allaire has spent the last year talking about a Circle project called Arc. An economic operating system, he calls it. A layer-one blockchain with a known validator set of major financial infrastructure companies. USDC as native asset. Sub-second finality. Built-in privacy primitives. No hard forks, no reorgs. Circle's payment network for orchestration. And, Allaire has been dropping hints, possibly a native Arc token at some point.

![Image](https://pbs.twimg.com/media/HHPQ2feWgAAqHdk?format=png&name=large)

Compare with Tempo. Known validator set of major financial infrastructure companies. Stablecoin-native gas. Sub-second finality. Privacy primitives. Payments-first.

Two of the largest crypto-adjacent companies in the world, running in parallel for most of 2025, independently converged on the same architectural answer: a permissioned layer-one blockchain where the validators are named financial institutions, where the native unit is a dollar-pegged stablecoin, and where the design target is enterprise payment reliability rather than censorship resistance.

If you are an institutional allocator, I think this is the single most important signal in the research. Two companies arriving at the same architecture independently is worth more than either company arriving at it alone. It says the market for institutional stablecoin settlement is a category, not a single-winner product. The category has a shape, and that shape is permissioned-L1 with known-FI validators.

This is also the observation that is hardest for me to write, because I currently work at the Ethereum Foundation. The piece could stop here and the takeaway for my own institution would be: The DeFi flows go to permissionless public chains. The enterprise B2B settlement flows, in the near term, do not. That is a real thing to name. Dankrad Feist, formerly an EF researcher, is now on the Tempo team and publicly backed the mainnet launch. The gravity is there.

The Tempo team has said previously, which I think is honest, is that all their engineering improvements to Reth flow back upstream to Ethereum and to the L2 ecosystem. The argument is that Tempo benefits Ethereum indirectly, even as it sits adjacent rather than inside. That is a real argument. For payments that move fast and don’t sit, I can see how this can make sense, for DeFi, Ethereum mainnet, more credibly neutral, makes better sense and that’s how I see the future of a multichain world.

One more thing on the Circle-Stripe competitive picture. In January 2026, during Davos week, the World Economic Forum held its flagship stablecoins panel. Jeremy Allaire was on it. The IMF was on it. Vera Songwe from the African development community was on it. Yat Siu was on it. Stripe was not. Not Patrick, not John, not Zach Abrams, not Matt Huang, nobody from Bridge or Privy or Tempo. The biggest stablecoin company by acquired footprint was absent multilateral policy venue in the world.

The Collisons have decided Stripe Sessions is their venue.

Not Davos, not the IMF, not central bank panels. That is a deliberate choice. Circle is accumulating policy-legitimacy capital with regulators and central banks. Stripe is accumulating developer and enterprise distribution. Eighteen months from now, when the next stablecoin regulatory framework gets written in Brussels or Singapore, Allaire will be in the room and the Collisons will not. Maybe Circle extracts specific regulatory carve-outs in the 2026-2027 international rulemaking cycle that Stripe has to retrofit into. The two companies' architectures look convergent. Their political postures are not.

## On the Triple Role

Matt Huang sits on Stripe's board. He is a managing partner of Paradigm, a $12.7 billion crypto VC fund. He is the CEO of Tempo (yes, reading that makes everyone else feel lazy), whose $500 million Series A Paradigm and Stripe both sat out (the round was led by Thrive and Greenoaks). Paradigm's portfolio includes Privy (Stripe-acquired), Phantom (Tempo issuer partner), Fireblocks (Tempo infrastructure partner), Chainalysis (Tempo infrastructure partner), and Farcaster (Romero and Srinivasan joined Tempo in February 2026).

The media pattern is suggestive rather than dispositive. Huang was comfortable doing long-form audio as a VC. He went on Invest Like the Best in April 2025, four months before becoming Tempo's CEO. Since he started as CEO at Tempo, his communications have been almost entirely controlled text channels: X threads, LinkedIn posts, the Paradigm blog, and a Colossus written profile in February 2026 (notable because Colossus also runs Invest Like the Best, and for Tempo he chose the text arm rather than the podcast arm). That may simply be discipline. It may also be legal posture.

**My prediction: when Huang breaks this pattern, the channel tells you the phase.** A regulatory venue (OCC conference, Treasury panel) means Tempo is shifting to institutional-legitimacy phase. A Stripe-controlled venue (Stripe Sessions, Cheeky Pint) means Tempo is being absorbed into Stripe's product narrative rather than running as a neutral entity. A crypto-native podcast (Bankless, Empire, Unchained) means something has gone wrong and it is damage control on the conflict question.

## What the Regulator Actually Cares About

The GENIUS Act, signed into law in July 2025, is the regulatory scaffolding under all of this. Two things about it matter for the Stripe story.

First, the Act bars non-financial public companies from issuing payment stablecoins directly without unanimous approval from a three-agency committee. The law did not literally pick Stripe for Meta. But it made the Diem path so politically and procedurally expensive that a partner-led stablecoin became the path of least resistance. Meta spent much of 2025 running a stablecoin partnership RFP. Stripe is reportedly the leading candidate to win it. The architecture is regulatory-shaped, not freely chosen.

There's a moment from Stripe Sessions 2025 with Mark Zuckerberg on stage with John Collison in May 2025, around the 42:20 mark of the recorded session on Stripe's YouTube channel. Referring to Diem, Zuckerberg says the quiet part out loud: "you guys are probably the much better company to do this." That is the CEO of the most-distributed consumer platform in the world, on his potential vendor's main stage, conceding the category. I don't think this was improvisation.

Second, and this is the subtler point, the OCC published a proposed rule in March 2026 that draws a specific line on yield-sharing. Arrangements where an issuer pays an affiliate, and the affiliate then passes yield to stablecoin holders, are presumptively prohibited. Arrangements where an issuer shares reserve economics with a non-affiliate white-label partner are not. The line is about holder-facing yield. B2B profit-sharing is untouched.

This protects Bridge's Open Issuance model. Bridge sharing the majority of reserve yield with Klarna (a licensed Swedish bank issuing its own stablecoin on Bridge's platform) is exactly the kind of non-affiliate profit-share the OCC rule leaves intact. What the rule goes after is programmes that route yield to end-users through affiliated intermediaries, which is closer to the Coinbase USDC rewards model. The active regulatory fight is not about Stripe's B2B stablecoin infrastructure. It is about whether consumer stablecoin wallets can offer interest in any form that looks like a bank deposit substitute. Stripe's position (B2B infrastructure, non-affiliate profit-sharing, trust charter rather than bank charter) is GENIUS-aligned by construction.

This is the single most important regulatory detail in the piece and it has been badly under-reported.

My prediction on the final rule, expected later in 2026: the non-affiliate language gets expanded, not narrowed. The OCC drew that line for a reason. I cannot prove who asked for it. But it is hard to miss who benefits from it. Stripe hired Cornerstone Washington for its GENIUS Act lobbying cycle. Cornerstone doesn't do general-purpose fintech lobbying. They do financial services regulatory carve-outs. That is not proof of authorship. It is a lobbying footprint exactly where you would expect one if Stripe's business model were the one being protected. When the final rule drops, Coinbase's USDC rewards programme will need to restructure. Bridge's Open Issuance economics will not.

If I am wrong, it is because Brian Moynihan's bank-deposit-flight argument carries the day at OCC. Watch the comment letters filed by the May 1st deadline. The ratio of banking-industry to fintech-industry letters is the leading indicator.

## Where the Bet Could Break

Four things, in rough order of probability.

The architectural bet might be wrong. Tempo and Arc assume that institutional payments will run on permissioned L1s. That might be true for the next five to ten years. It might also be the blockchain-consortium moment that enterprise software has seen repeatedly over the last decade (R3 Corda, Besu, JPM Quorum) where the consortium chain becomes a niche settlement layer and the actual volume migrates to public rails as those public rails mature. If Ethereum's rollup ecosystem continues its reliability and throughput progress before Tempo solves its adoption issues, the architectural bet looks different.

Stripe owning issuance, orchestration, wallet, settlement chain, and trust charter inside one structure is a lot of control points. If any of those layers has a serious operational failure, the blast radius is larger than it would be in a less vertically integrated setup. Regulators tend to notice this kind of concentration once it starts to matter.

The structural integration of Tempo, Paradigm, and Stripe is the area where institutional adoption may face questions. Huang's triple role is, as far as I can tell, being handled thoughtfully by serious people. Clarity is something Tempo can choose to provide, on its own timeline, before it becomes a question someone else asks first.

The consortium is softer than it looks. Mastercard is a Tempo design partner and simultaneously just spent up to $1.8 billion acquiring BVNK, which is a direct Bridge competitor. That is at least not a clean vote of confidence. **My prediction: Mastercard quietly withdraws from the Tempo design partner list within twelve months, or pressures Tempo to make BVNK compatible at the rail level.** The Mastercard-Tempo relationship is a legacy position from the September 2025 design partner announcement. It will not survive BVNK integration. When you see Mastercard stop being named in Tempo partner announcements, that is the withdrawal happening without a press release.

Visa is a different story. Anchor validator, MPP extension written by its own engineering team, a six-month in-house build before the April 2026 validator announcement. Visa is going in deep. But even Visa hedges. It is also a named participant in the x402 Foundation. Every major consortium member is hedging. The Tempo governance narrative assumes the partners stay on the chain. They will stay as long as the commercial terms and the settlement rails make sense for them. They will not stay for strategic loyalty.

Sessions 2026 ran on April 29 as I was finalising this piece. The opening keynote put the architecture on a stage. Patrick Collison framed the moment as the entire economy replatforming. Will Gaybrick demonstrated streaming payments live, settling thousands of sub-cent stablecoin transactions on the Tempo Block Explorer in front of 9,000 people, and called it "the world's first streaming payments business." Henry, who runs Privy inside Stripe, used his segment to reframe the entire stack. "This work is not about crypto. For crypto's sake. It's about enabling you to build fundamentally better experiences for your customers, your users and their money." Konstantopoulos appeared as Tempo's public voice. Matt Huang did not. Shopify announced it would join the Tempo validator set. Klarna USD is live as a Bridge-issued branded stablecoin. The watch signals are tracking.

## The Bet

Stripe is not making a crypto bet.

If Tempo works, Stripe owns the settlement layer. If Tempo disappoints, Stripe still owns Bridge, Privy, the charter path, the merchant relationship, and the dashboard where the money shows up. If Meta picks Circle, Stripe still owns the developer and merchant layer that both Meta and Circle have to touch.

That is the part that makes this strategy hard to compete with. The chain can be early, small, or even wrong in parts. The touch points remain.

The thing to watch next is when the second-order ecosystem forms. Consultants, systems integrators, compliance tooling vendors, ERP plug-ins. Tempo's stablecoin advisory service is the opening move. Visa Consulting has just spun up its own stablecoin advisory practice. When this becomes a real consulting category, the architecture question will be closed and the implementation question will be open, and the company with the deepest control-point coverage across issuance, orchestration, wallet, and settlement will have the highest margins.

That company, today, is Stripe. Whether it is still Stripe in three years depends on things I cannot see from here. Whether Meta's partnership lands. Whether the OCC trust charter gets to final approval. Whether Tempo's validator set decentralizes in a way that the market finds credible.

The question is not whether Stripe becomes crypto-native. It is whether crypto becomes Stripe-native before enterprises notice the difference.

Much to my bloodline's disappointment, I have no commercial relationship with Stripe, Bridge, Privy, Tempo, Paradigm, Circle, Mastercard, Visa, or any of the other companies named in this piece. No payment, in-kind or otherwise, has been received.