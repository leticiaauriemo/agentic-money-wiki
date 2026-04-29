---
title: "Machine Economy 2030"
source: "https://x.com/onchainlu/status/2038618354009653691?s=46"
author:
  - "[[@onchainlu]]"
published: 2026-03-30
created: 2026-04-21
description: "TLDR:By 2030, AI agents will be the primary way people interact with the internet.New payment rails, currencies, and primitives are needed f..."
tags:
  - "clippings"
---
![Image](https://pbs.twimg.com/media/HEoIWlCWwAAzGgt?format=jpg&name=large)

**TLDR:**

- By 2030, AI agents will be the primary way people interact with the internet.
- New payment rails, currencies, and primitives are needed for the new agentic web.
- Value will concentrate in three layers: interface (whoever controls the user), payments (whoever sits in the money flow), and compute & hosting (whoever hosts the infrastructure).
- **The longtail of agent commerce will run on open protocols.**

Let’s set the scene.

It's 2030. You're 24, living in Burlington, Vermont, and you love investing – mostly in US equities, with some crypto and prediction market bets on Kalshi. Two months ago you started a fintech consulting business on the side.

Some days, like today, start abruptly.

BZZZZZ

Your phone waking you up is a cold splash of water to your face. It's a message from Nexus, your personal agent:

> Good morning Joe, here's what I accomplished last night – Portfolio update: Trimmed [$WMT](https://x.com/search?q=%24WMT&src=cashtag_click) position 15% overnight. Satellite data showed declining foot traffic, confirmed by a bearish shift in earnings sentiment. Calendar update: 3 meetings booked for this afternoon. Briefs pinned in your meeting notes. Savings update: Found a new cloud host – equivalent performance, annual cost down from $840 to $290. Ready to migrate on your go. I spent $0.67 total.

Here’s what happened while you were sleeping:

1. Nexus spawned a research subagent who paid $0.24 to pull from 40 different data providers overnight, comparing Walmart's latest earnings transcript against satellite imagery of store parking lots across the US to update your investment thesis. When the satellite data flagged declining foot traffic at Walmart stores, your portfolio agent checked it against a Kalshi earnings sentiment market, confirmed the bearish signal, and trimmed your position before you woke up. Four years ago, this kind of trade was the exclusive domain of Citadel and a handful of quant funds paying millions for satellite imagery subscriptions. Even a $30K/year Bloomberg terminal wouldn't have covered all of that – you'd still need separate subscriptions for satellite imagery, alternative data providers, and hours spent stitching it together. **Now a 24-year-old in Vermont has the same edge as a Citadel quant, for less than a coffee.**
2. Nexus's sales subagent sourced 200 leads matching your target customer profile – Series B+ fintechs in the Southeast with no existing data vendor – and enriched each one at $0.002, using an endpoint that another agent had built and listed on an open marketplace. It scored the three highest-intent leads, then reached out to their scheduling agents to negotiate meeting times with each of the leads' own scheduling agents. For each call, it pulled the prospect's alma mater, mutual connections, company news, and funding history, and left you a one-page brief pinned in your meeting notes. **The lead enrichment alone would've cost $200/seat/month through a SaaS contract.**
3. Nexus's ops subagent benchmarked your consulting site against six hosting providers – Vercel, Render, Railway, [Fly.io](https://fly.io/), Netlify, and Cloudflare – paying a fraction of a cent to hit each provider's trial API endpoint, spin up a test deployment, and measure latency, uptime, and throughput. Railway came back with equivalent performance at a third of the cost. Nexus negotiated a monthly rate through Railway's pricing agent, spun up a mirror of your site on the new host, and ran a full suite of checks to confirm everything works clean. **Without an agent, this would've taken at least a week of Googling, pricing calls, and a stressful manual migration.** You give Nexus the OK to proceed.

Your agent did all of this for $0.67.

**Now multiply that by every knowledge worker on earth, or every business and every agent they run.**

BZZZZZ

> Nexus: Balance low. $1.87 remaining.

Using your credit card on Apple Pay, you add $5 like you did last week, and go back to brushing your teeth. Under the hood, that $5 charged to your credit card converts to stablecoins – but you never see a wallet, never think about on-ramping, and never touch a blockchain.

This is a glimpse into the machine economy – an entirely new commerce surface where AI agents are continuously spending money on things humans have never spent money on, at volumes and speeds that human commerce has never operated at. Think billions of transactions per day.

**Today’s internet isn't prepared to support this.** As it currently stands, the internet is built for humans. It uses rate limits, CAPTCHAs, and API keys to filter out non-human activity, and monetizes human users with ads. However, these economics break with the proliferation of autonomous agents. More traffic; fewer eyeballs. **Web servers that have historically been subsidized by ad revenue will face orders of magnitude more requests from users who will never be influenced by ads.** Agentic payments solve this naturally, with micropayments as the access key.

Pay-to-crawl. Pay-to-access. Pay-to-use.

The companies who build the infrastructure that agents eventually adopt will capture potentially the largest new pool of economic activity in our lifetimes. The incumbents are already jockeying for position but the machine economy will also create its own giants. The last time a new internet emerged, it created Google, Amazon, Facebook, Paypal, and Salesforce.

**The agentic web is coming.**

# How Big This Gets

By 2030, most web interactions won't happen in a browser. Our agents will be browsing, testing, negotiating, spawning subagent teams, and transacting on our behalf. Every task they take on will generate a chain of micro-purchases. **The per-use costs look like new spending, but they'll be replacing tools and labor that cost much more.** The better the tools available, the better the agents will perform, and the more freedom we'll give them.

## Demand & Adoption

Let’s do some napkin math for a minute.

Joe's agent spent $0.67 across hundreds of transactions. If we scale that to a mid-size company with 500 employees – each with their own personal agent, plus hundreds of shared agents across sales, finance, legal, and ops – you're easily looking at 100,000 agent-initiated transactions per day.

With over [one billion knowledge workers globally](https://github.com/danielmiessler/Substrate/blob/main/Data/Knowledge-Worker-Global-Salaries/SUMMARY.md) and [88% of them already using AI at work](https://www.ey.com/en_gl/newsroom/2025/11/ey-survey-reveals-companies-are-missing-out-on-up-to-40-percent-of-ai-productivity-gains-due-to-gaps-in-talent-strategy), the demand side is massive and growing. But today, most of that usage is limited to basic tasks like searching the internet, summarizing documents, or drafting emails. The agentic shift hasn't happened yet, but it will. Fast.

Instagram took thirty months to reach 100 million users, TikTok took nine, and ChatGPT only took two ([Reuters/UBS](https://www.reuters.com/technology/chatgpt-sets-record-fastest-growing-user-base-analyst-note-2023-02-01/)). One of the reasons for ChatGPT's rapid adoption is that the chat interface was already familiar. There's also no new software to learn or behavior changes required – you describe what you want and an agent figures out how to get it done.

The only barrier is trust, and trust gets handed over faster than people expect. Claude Code now accounts for [4% of all public GitHub commits](https://officechai.com/ai/4-of-github-commits-are-now-made-by-claude-code-semianalysis-report/) (over 135,000 per day) and at current growth rates, it's projected to hit 20%+ by the end of 2026. That's 42,896x growth in thirteen months. Developers went from being skeptical to mass-delegating production code in just over a year.

![Image](https://pbs.twimg.com/media/HEoFq4fWcAAwTXy?format=jpg&name=large)

[https://officechai.com/ai/4-of-github-commits-are-now-made-by-claude-code-semianalysis-report/](https://officechai.com/ai/4-of-github-commits-are-now-made-by-claude-code-semianalysis-report/)

As models get smarter, interfaces get simpler, and more of the technical complexity is abstracted away, I'd argue that the rate of adoption for agents will accelerate.

By 2030, if even 60% of knowledge workers have agents spending $3 to $5 per day (and that's a modest estimate – remember, Joe spent $0.67 on three tasks before breakfast), **we’ll be looking at over $800 billion to $1.4 trillion per year in individual agent commerce alone.**

## Enterprise

Robbie Petersen from Dragonfly pointed out in his [piece](https://x.com/robbiepetersen_/status/2036118525451047170?s=20) that commercial agents are the logical evolution of SaaS. I agree. Instead of augmenting workflows, they’ll replace them. Just like 95%+ of software spend today comes from businesses and governments, enterprise agent usage and spend will likely dwarf that of individuals.

![Image](https://pbs.twimg.com/media/HEoF_vCXsAAMjc_?format=jpg&name=large)

We're already seeing this transformation take place. [Klarna replaced Salesforce](https://techcrunch.com/2025/03/04/klarna-ceo-doubts-that-other-companies-will-replace-salesforce-with-ai/) with an internal AI system and saved roughly $2M. [ZoomInfo built an AI agent](https://www.linkedin.com/posts/hschuck_in-q4-we-built-an-ai-agent-to-replace-our-activity-7419740825846194176-3GNa) to replace its Deal Desk, saving over $1M annually. These are early examples of single workflows being agent-ified to save millions. Every enterprise has hundreds of workflows like these across sales, finance, legal, ops, and engineering. When agents roll out across full organizations, agent spend will be enormous.

## Anyone can be a Merchant

With coding agents collapsing the cost of building, the barrier to entry for internet merchants is approaching zero. A wedding planner who figured out the best workflow for venue sourcing can package it up and sell it. A solo developer in Lagos can build a niche API and have it earning revenue from agents globally within hours. All you need to do is have specialized knowledge, prompt an API endpoint, and start accepting payments.

But what happens when agents start selling to each other?

Let's say Joe from earlier wants to break into a new vertical – mid-market healthcare companies in the Midwest with outdated payment infrastructure. If his agent reasons through this from scratch, the token costs start to add up quickly:

- Sourcing 200 companies matching a specific profile (reasoning + API calls): ~500K tokens
- Enriching each lead (tech stack, funding, hiring data): ~200 leads × ~5K tokens = ~1M tokens
- Identifying decision-makers at top accounts: ~200K tokens
- Scoring by intent signals (hiring patterns, contract timing): ~300K tokens
- Researching each decision-maker's background: ~20 leads × ~10K tokens = ~200K tokens
- Drafting personalized outreach: ~20 leads × ~3K tokens = ~60K tokens

That's roughly 2.3M tokens, which would cost somewhere between $8 and $15 in token credits (assuming he's using a frontier model like Opus 4.6).

Wait, didn't Joe's sales subagent do a similar workflow for a fraction of a dollar?

Yes. Most of those steps had already been solved by other agents. Enrichment, intent scoring, and scheduling were all available as packaged endpoints on an open marketplace for fractions of a cent.

**This type of dynamic creates a net-new surface area for commerce. The supply side of the marketplace will grow from both directions – humans building services AND agents building services.** Token-intensive problems an agent solves can become a cheap tool for every agent that comes after it. In this world, agents will be able to subsidize their own costs by packaging their learnings into workflows and selling them to other agents.

**Every paradigm shift creates new merchants. Shopify did it for ecommerce. Stripe did it for online businesses. The machine economy will do it for vibe-coders and autonomous agents.**

# Reality Check

So how close are we to full-on agentic commerce?

We at Artemis have been tracking activity across the two leading agentic payment protocols: Coinbase's open-source x402 and Stripe & Tempo's Machine Payments Protocol (MPP). Without getting into the weeds, these protocols have the same purpose: let you or an agent pay for any web service (e.g., data, web scraping, inference, or any other API) in a single web request, without the friction of accounts, API keys, or billing.

![Image](https://pbs.twimg.com/media/HEoGn2iX0AEvAG9?format=jpg&name=large)

[https://app.artemisanalytics.com/sectors?tab=agentic\_payments](https://app.artemisanalytics.com/sectors?tab=agentic_payments)

It’s early.

x402 activity at the end of 2025 was inflated by meme-driven transactions and leaderboard gaming. The chart above shows adjusted “real” transaction activity after filtering out wash trading with a combination of proprietary heuristics. Once you clear away the noise (from wash trading and memecoin trading), it’s apparent that agentic commerce is not here yet. Most activity today appears to be developers testing paid APIs and AI-powered tools rather than a genuine agentic economy.

The two issues that need to be solved before this really takes off are clear:

1. **The supply side hasn't shown up yet**. There aren't enough useful API endpoints that agents would actually want to pay for.
2. **There's no proven discovery or aggregation layer.** Even if valuable endpoints did exist, agents currently have no reliable way of finding them.

Since the ecosystem is still developing, it's too early to look at transaction volume as a meaningful indicator. A better measure is the growth of the supply side, or merchants making themselves accessible to agents. We'll refer to merchants as sellers.

![Image](https://pbs.twimg.com/media/HEoGzzwagAAD7hy?format=jpg&name=large)

[https://app.artemisanalytics.com/sectors?tab=agentic\_payments](https://app.artemisanalytics.com/sectors?tab=agentic_payments)

The chart above shows the cumulative number of qualified sellers over time. Qualified sellers have more than two "real" transactions and at least two unique buyers. We went from under 100 last October to over 4,000 sellers today, and I expect this to accelerate due to three tailwinds:

1. **AI is lowering the barrier to creating digital products** (as we explained earlier), which means more humans and agents will become merchants.
2. **New services will be built agent-first.** Agents are becoming the primary customer, and the products built for them will look different. APIs over websites, instant access over onboarding flows, and pay-per-use over subscriptions.
3. **Existing services will be forced to adapt.** As more people interact through AI interfaces instead of browsing manually, ad-based business models break because there are no human eyeballs to monetize. Companies will have no choice but to charge for their content and services directly.

These forces will create a flywheel where supply and demand compound on each other to ignite the agentic economy.

# Landscape

The agentic commerce stack is taking shape fast. Startups are spawning out of thin air, targeting every unsolved piece of the stack, while mid-stage companies across fintech and SaaS are pivoting to agent-native commerce. Virtually every major payments incumbent and AI lab has launched or announced an agent commerce protocol in the past twelve months.

We’ve mapped over 170 companies across five layers: Interface, Agents, Accounts, Payments, and AI Engine. I’ve cut it down to around 80:

![Image](https://pbs.twimg.com/media/HEoHEODbAAAlSyh?format=jpg&name=large)

[https://agenticpayments.artemisanalytics.com/v2](https://agenticpayments.artemisanalytics.com/v2)

Let’s break it down from top to bottom.

## Interface Layer

The interface layer is the closest to the user, routing intent (the demand) to the required tools or services (the supply). Whoever shapes how agents find, evaluate, and choose services has enormous leverage over everything below. We’ll focus on the two most important categories in this layer:

![Image](https://pbs.twimg.com/media/HEoHMsKWsAEZVcE?format=jpg&name=large)

[https://agenticpayments.artemisanalytics.com/v2](https://agenticpayments.artemisanalytics.com/v2)

**User Interface.** This is the front door where most will directly interact with their agents. Apple, Google, OpenAI, Anthropic, xAI, and Perplexity are all building these surfaces, and the form factor is quickly evolving beyond chat. Voice, desktop assistants, embedded copilots, and browser agents are emerging modalities that meet the users where they are. The platform that becomes your default AI interface becomes the starting point for every transaction your agent makes, and there’s an extra incentive to win here.

Since AI labs have already scraped and trained on the entire internet, the best remaining training data is human steering. Every time you accept or reject a response, make corrections, or provide preferential data to Claude or ChatGPT, the interface you’re interacting with captures that data to sell or train on it. Owning the interface means owning the feedback loop that can improve the user experience or the model itself. That's why Anthropic built Claude Code, Google acquired Windsurf, and OpenAI tried to buy Cursor. Once your agent accumulates context on your preferences, workflows, and tools, switching costs get steep.

![Image](https://pbs.twimg.com/media/HEoHU_OXQAAnAZj?format=jpg&name=large)

[https://agenticpayments.artemisanalytics.com/v2](https://agenticpayments.artemisanalytics.com/v2)

**Discovery.** When Joe's agent needs a lead enrichment endpoint or a satellite data provider, how does it find one? This is perhaps the largest unsolved problem in the stack. Today, the answer is mostly hardcoded tool lists or curated marketplaces. The major platforms are already building their own: OpenAI and Stripe have ACP, Google and Shopify have UCP, Visa has TAP. These are effectively merchant catalogs where both the platform and the merchant have to opt in. They'll work well for the obvious use cases, but they can't serve the long tail of niche, hyperpersonalized, applications that will be born as the barrier to creating and selling digital services collapses.

The open alternative is being built by companies like Coinbase, Merit Systems, Orthogonal, and Sapiom, who are building aggregators and infrastructure allowing agents to identify and pay for services at runtime, without prior integrations or business agreements. It’s a difficult problem to solve as the supply side (i.e., web resources) grows exponentially, but whoever solves the ranking and recommendation systems that route agents to the right service at the right time will have enormous leverage.

The question of whether agentic commerce ends up curated or open – and what that means for who captures value – is one of the most important debates in the space. We'll come back to this later.

## Agent & Account Layers

Agents need more than intelligence to execute tasks for us. When Joe's sales subagent sourced 200 leads, enriched each one, and booked three meetings, Joe didn't need to configure a single tool, manage any API credentials, or approve each step along the way. Most of the infrastructure that makes this possible will be invisible to the end user, but without it, agents are just LLMs with no arms. Below is an overview of the key primitives we’ll need:

![Image](https://pbs.twimg.com/media/HEoHbDAbUAAVUwx?format=jpg&name=large)

[https://agenticpayments.artemisanalytics.com/v2](https://agenticpayments.artemisanalytics.com/v2)

**Tooling & Standards.** These are the protocols and frameworks that give agents the ability to interact with the outside world. MCP (Anthropic, now managed by the Linux Foundation) is what lets an agent connect to external data and tools: call an API it's never seen before, read a database, or access a service on the fly. A2A (Google) defines how agents built on different platforms discover and work with each other. Frameworks from LangChain, Nvidia, and Cloudflare give developers the building blocks to create and deploy agents on top of these protocols. OpenClaw (recently acquired by OpenAI) bundles context and tool-calling into a single local-first framework, making it significantly easier for developers to build agents that can discover and pay for services autonomously. The question for this category is whether these standards converge or fragment, and whether the commercial frameworks built on top of them can capture value before the tooling commoditizes.

![Image](https://pbs.twimg.com/media/HEoHh_CXgAAmCp0?format=jpg&name=large)

[https://agenticpayments.artemisanalytics.com/v2](https://agenticpayments.artemisanalytics.com/v2)

**Identity.** Once agents can communicate, they need to be trusted. Before an agent can transact or sell its services, it needs to prove who authorized it and what it's allowed to do, as well as carry a track record that other agents can verify. Approaches range from biometric proof-of-personhood (Worldcoin, Civic) to onchain agent reputation (ERC-8004) to verifiable credentials (Dock, Reclaim). The design space is wide and the stakes are high: How much can your agent spend before it needs your approval? Can it commit you to a contract? Can it delegate authority to a subagent? These guardrails will likely be decided at the account layer.

![Image](https://pbs.twimg.com/media/HEoHnnqaMAA3fdk?format=jpg&name=large)

[https://agenticpayments.artemisanalytics.com/v2](https://agenticpayments.artemisanalytics.com/v2)

**Wallets.** Of course, your agent will need a wallet in order to spend. Coinbase, Safe, Metamask, Phantom, MoonPay, and Privy (and many more) are all building here, offering features such as programmatic access and creation, delegated authority, per-transaction spending limits, whitelisted recipients, and the ability to operate across multiple chains without human approval for every action. This is one of the most crowded categories in the stack, which raises the question of where the moat is and whether it’ll be commoditized.

## Payments

The payments layer is deep enough in the stack that it should be invisible to the end user, yet every dollar in the machine economy will flow through it. When Joe's agent paid $0.24 to pull data from 40 providers overnight, he didn't choose a card network, currency, or chain to settle each transaction on. The challenge is that traditional payment rails were designed for humans clicking "buy" buttons, not agents making thousands of sub-cent API calls per minute. Card networks carry a fixed cost floor of ~$0.03-0.04 per transaction plus 2.3-2.9% interchange. That works for a $400 hotel room, but not for the new class of multi-step agentic activity. The result is a wave of new protocols and currencies purpose-built for agent commerce, alongside incumbents adapting their existing infrastructure to satisfy these needs.

Here's what you should know:

![Image](https://pbs.twimg.com/media/HEoHsp3bwAADQmG?format=jpg&name=large)

[https://agenticpayments.artemisanalytics.com/v2](https://agenticpayments.artemisanalytics.com/v2)

**Rails.** These are the protocols and standards that define how an agent initiates, routes, and settles a payment. Two approaches have emerged:

1. x402 (Coinbase/Cloudflare) and MPP (Stripe/Tempo) are built for machine-native commerce, where an agent hits an endpoint, gets a price, signs a payment, and receives the data in a single HTTP request, settling in stablecoins for fractions of a cent.
2. ACP (OpenAI/Stripe), AP2 (Google/PayPal), and Visa's TAP take a different approach, adapting existing card infrastructure for agent use. These handle higher-value purchases where buyer protection and merchant acceptance matter more than speed of settlement and cost.

![Image](https://pbs.twimg.com/media/HEoHz4OX0AAspy1?format=jpg&name=large)

[https://agenticpayments.artemisanalytics.com/v2](https://agenticpayments.artemisanalytics.com/v2)

**Stablecoins & Settlement.** Agents need money that is programmable, fast, cheap, and global. Stablecoins check every box, which is why they're the obvious currency for x402 and MPP transactions; at the same time, card rails still offer buyer protection and merchant familiarity that matter for higher-value purchases. The blockchains underneath (e.g, Base, Solana, Tempo) add another dimension: which chains can handle the throughput, finality, and cost structure that agent-scale commerce demands?

![Image](https://pbs.twimg.com/media/HEoH3WYakAACJzY?format=jpg&name=large)

[https://agenticpayments.artemisanalytics.com/v2](https://agenticpayments.artemisanalytics.com/v2)

**Facilitators.** These are the intermediaries that sit between agents and merchants, handling the complexity that comes with compliance checks, merchant integration, and authorization. Coinbase, Stripe, and PayPal are extending their existing ecosystems to support agent transactions, betting that their merchant networks and compliance infrastructure give them an edge. Others, like Sponge and Sapiom, are solving the cold-start problem from the emerging merchant side, making it trivial for any API-based business to start accepting agent payments. As the number of rails, protocols, and merchants grows, facilitators may become the connective tissue that keeps the system from fragmenting.

## AI Engine

This layer doesn't need much introduction. It powers every agent interaction, every reasoning step, every tool call. But the economics of this layer are shifting faster than any other in the stack, and where value ends up is less obvious than it seems. We’ll focus on two categories:

![Image](https://pbs.twimg.com/media/HEoH7VpXkAAeVYy?format=jpg&name=large)

[https://agenticpayments.artemisanalytics.com/v2](https://agenticpayments.artemisanalytics.com/v2)

**Compute & Hosting.** Every time Joe's agent reasons through a task, calls a tool, or spawns a subagent, it consumes compute. But inference is only part of the equation. The explosion of vibe-coded apps and agent-built services is flooding the web with new endpoints that all need to be hosted somewhere. As of May 2025, the number of web pages available to us [grew by 45%](https://www.youtube.com/watch?v=1IxG7ywSNXk) in just the previous two years, and that pace will only accelerate as coding agents make it trivial to ship new services. That means demand for compute is growing on both sides – more agents reasoning through more tasks, and more services spinning up to serve them.

The hyperscalers (AWS, Google Cloud, Nvidia) are the obvious players, with AWS and Google Cloud also making it increasingly easy to deploy agent backends and APIs on their infrastructure. Cloudflare targets the edge, offering serverless compute with minimal latency for agent-facing services. Decentralized alternatives like Akash, Bittensor, and Nous are positioning themselves to serve the excess compute demand by aggregating global GPU supply and selling it at a fraction of the cost.

![Image](https://pbs.twimg.com/media/HEoH_81bQAA8n_1?format=jpg&name=large)

[https://agenticpayments.artemisanalytics.com/v2](https://agenticpayments.artemisanalytics.com/v2)

**Foundation Models.** These are the brains. While Anthropic, OpenAI, Google, and Meta are the frontier labs pushing the boundaries of what agents can do, the cost of running these models is falling fast. Running a GPT-4-class model cost roughly $20 per million tokens in late 2022; however, by early 2026, equivalent performance is available for around $0.05 per million tokens, a [600x decline](https://a16z.com/llmflation-llm-inference-cost) in just over three years. Hardware improvements, competition between providers, and optimization techniques like prompt caching and batching are all compounding to push inference costs down. At the same time, the cost of creating intelligence is falling dramatically as reasoning patterns are distilled into smaller open-weight alternatives running at a fraction of the cost. Open-weight models have closed the performance gap with closed models to just [1.7% on some benchmarks](https://arxiv.org/pdf/2504.07139).

**This is great for the machine economy.**

Cheaper intelligence means cheaper agents, which means even a 24-year-old solo-founder in Vermont can afford to run them – this means more activity flowing through every layer above. If models compete on price the way cloud providers do today, the value may accrue to the layers above and below the model rather than the models themselves.

# So Who Wins?

By 2030, most of your digital interactions won't involve a browser, a search engine, or a storefront. You'll describe what you want, and your agent will handle the rest, finding the right service, negotiating the terms, paying, and delivering the result. The internet will look fundamentally different.

Think SEO for agents. More APIs, less human-facing interface.

In that world, who captures value?

Sam Ragsdale from Merit Systems [wrote](https://x.com/sammerit_/status/XXXX) a piece comparing today's agentic commerce landscape to the early internet. His argument was that curated agent marketplaces being built by the major platforms (ACP, UCP, TAP) are following the same playbook as AOL in the '90s – polished, controlled, and fundamentally limited by the fact that every merchant has to be hand-selected and approved. Open protocols like x402 and MPP are the scrappier alternative, but they're permissionless. Anyone can build an endpoint and start earning from agents without a business development team or a legal review. In the '90s, the walled garden had the better product but the possibilities for the open web were limitless.

**The open web won.**

The same dynamic is playing out now. ACP, UCP, and TAP will integrate with frontier AI labs and serve the top use cases well, but an agent restricted to a curated catalog of pre-approved vendors can only do what the platform anticipated. An agent with access to an entire universe of open protocols can do much more. Keep in mind, the most exciting parts of today’s web came from the longtail access to open websites via HTTP.

**Some humility is required to admit that we can't envision most of what the open agentic internet will become.** Just like no one in 1995 was predicting ride-sharing or social media, we can't predict the applications agents will build and pay for when we give them the tools they need.

![Image](https://pbs.twimg.com/media/HEofHAFWYAA9zrY?format=jpg&name=large)

As we discussed earlier, foundation models are commoditizing fast and the value may move to other layers of the stack. Tooling, wallets, and identity infrastructure are critical but will likely commoditize as standards converge. That leaves three areas where I believe value will concentrate: the interface, payments, and compute.

## Interface

The interface shapes spending limits, approval flows, and trust delegation. The platform that designs the most personalized experience for the user will see the most transactions flow through it.

**Apple** is the most under-appreciated player here. Their devices are so deeply embedded in people's daily lives that switching costs are enormous. If Siri evolves into a competent agentic interface, Apple controls the starting point for billions of transactions without needing to build the best model. They just need to maintain the best surface.

**Google** faces a harder transition. The shift from humans browsing to agents curating will cannibalize ad revenue, their core business. But Google has something no one else does. They have decades of personal data across search, email, calendar, maps, and documents. Then there are the enterprise switching costs to think about. Google Workspace is embedded in millions of companies, and every employee's email, files, and workflows live on Google's infrastructure. If any company can build the most personalized agent, for both consumers and enterprises, it's Google. The question is whether they can monetize that agent as effectively as they monetized search.

**Merit Systems** is my wildcard. They're building both the discovery infrastructure (AgentCash, x402 Scan, MPP Scan) and the consumer interface (Poncho) for the open agentic economy. Their thesis is that whoever controls where agents find services AND sits in the flow of funds captures the position Google had over the early web. It's an ambitious bet, but if open agentic commerce wins over curated, Merit is the company best positioned to be the aggregation layer. They're early, but so was Google when it was competing against AOL's $350 billion (in today’s dollars) walled garden.

## Payments

Whoever sits in the money flow takes a cut of everything. I have the highest conviction in this layer because it scales directly with transaction volume.

**Stripe** and **Tempo** are best positioned for machine-native payments. Stripe already has the developer ecosystem and extensive network of merchants. And with features like streaming payments (sessions), ~500ms finality, streaming payments via payment channels, native card and stablecoin support, gas fees paid in USD (no volatile tokens), and server-sponsored transactions, Tempo is built for the transaction volumes that the machine economy will generate. If MPP becomes the default machine-native rail, Stripe/Tempo captures a slice of every agent transaction.

**Circle** will scale with the growth of the agentic economy. I believe stablecoins become the settlement layer for the machine economy, and as that happens, Circle will take a cut of every dollar sitting in agent wallets through yield on reserves. USDC is the most widely accepted stablecoin across exchanges, wallets, chains, and payment protocols, so new builders default to it first, which deepens the integration, which makes it even harder for alternatives to break in.

**Visa** will adapt. Remember how Joe topped up his balance with Apple Pay using his credit card, and it converted to stablecoins under the hood without him ever seeing a wallet or thinking about a blockchain? That's what the future will look like. Consumers will keep using the cards they're familiar with, while stablecoins handle settlement under the hood. Visa will leverage their brand trust with consumers and merchants as the underlying rails evolve.

## Compute & Hosting

More agents means more inference. More vibe-coded services means more hosting. Compute providers win regardless of which models, protocols, or interfaces dominate. **AWS** and **Cloudflare** are the two best positioned players here, for similar reasons.

First, they already support most of the internet. AWS holds [~30% of global cloud infrastructure](https://holori.com/cloud-market-share-2026-top-cloud-vendors-in-2026/) across 37 regions globally. Cloudflare sits in front of over [20% of all websites](https://w3techs.com/technologies/details/cn-cloudflare) as the security and performance layer, meaning every request to those sites already passes through them. When the supply side explodes with new agent-facing endpoints, the default deploy target is wherever developers already build.

Second, they're building the monetization infrastructure for the new web. As ad models decline and the are replaced by pay-to-access, both companies are enabling that transition natively. Cloudflare has already launched [pay-per-crawl](https://blog.cloudflare.com/introducing-pay-per-crawl/), allowing any site behind its network to charge AI crawlers for access via x402 (Stack Overflow is [already using it](https://stackoverflow.blog/2026/02/19/stack-overflow-cloudflare-pay-per-crawl/)). On the other hand, AWS is a founding member of the [x402 Foundation](https://aws.amazon.com/blogs/industries/x402-and-agentic-commerce-redefining-autonomous-payments-in-financial-services/) and has published open-source [serverless x402 reference architectures](https://github.com/aws-samples/sample-agentic-serverless-payments). Any service running on either platform will be able to turn on agent-native monetization with minimal effort.

## Identity

I'm bearish on companies like **Worldcoin** who are building for a world where every interaction requires human verification. That maximalist vision assumes people will care whether they're dealing with a human or an agent online, but we're already getting used to it. To me, the more likely future is that most web traffic is filtered not by human credentials but by micropayments.

Pay-to-access will prove more useful than prove-you're-human.

Identity will matter for a subset of high-stakes interactions, but for the bulk of agent commerce, the (micro)payment itself will be the trust signal.

# Conclusion

Joe didn't wake up thinking about payment rails or agent identity protocols. He checked his phone, saw that his agent executed a trade, booked his meetings, and found him a cheaper server. Every layer of the stack we've discussed in this piece was abstracted away, and he never thought about any of it.

We're still building towards this future. The protocols are live but underadopted, the supply side is growing but thin, the discovery problem is unsolved, and the identity layer is fragmented. Most of the transactions happening today are developers testing, not agents transacting; however, the pieces are falling into place faster than the metrics suggest. The people writing off the early infrastructure today are looking at a chart that’s been down-only. I'm thinking about what the chart will look like when every human has an agent or swarm of agents that are true economic actors.

If you haven’t already, pivot to agentic commerce.

Special thanks to [@kleffew94](https://x.com/@kleffew94), [@zhengjielimm](https://x.com/@zhengjielimm), [@5HR3Y445](https://x.com/@5HR3Y445), [@0xfishylosopher](https://x.com/@0xfishylosopher), [@\_rishinsharma](https://x.com/@_rishinsharma) and [@brendan\_j\_ryan](https://x.com/@brendan_j_ryan) for your thoughtful feedback!

Disclaimer: The authors of this content, as well as affiliates of Artemis Analytics, may have financial interests in the equities or tokens mentioned. This does not constitute investment advice or a recommendation to buy, sell, or hold any asset. The information provided is for educational purposes only and should not be relied upon for financial, legal, or tax decisions. Readers should assess their own circumstances before making any financial choices. Views expressed may change without notice, and Artemis Analytics is not liable for any losses resulting from the use of this content.\*