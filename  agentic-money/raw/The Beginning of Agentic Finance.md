---
title: "The Beginning of Agentic Finance"
source: "https://x.com/castle_labs/status/2047316059842388221"
author:
  - "[[@castle_labs]]"
published: 2026-04-23
created: 2026-04-28
description: "Chapter 1: Everything is going AgenticOnly a few years remain before Artificial Intelligence (AI) systems surpass humans in most cognitive t..."
tags:
  - "clippings"
---
![Image](https://pbs.twimg.com/media/HGmEOvjaUAAsDlR?format=jpg&name=large)

# Chapter 1: Everything is going Agentic

Only a few years remain before [Artificial Intelligence (AI) systems surpass humans in most cognitive tasks](https://americanbazaaronline.com/2026/02/19/anthropic-ceo-says-ai-will-exceed-cognitive-capabilities-of-humans-475468/). With the advent of computers and AI, our civilisation might no longer be a human’s world.

AI is good at researching, code generation, software development, planning, video and image editing/generation, and multiple other tasks. One of the things humans are not very comfortable letting go of is finance. Within this context, the narrative of agentic payments has grown too large to ignore. This is not an abstract forecast, but an industrial reality poised to reshape how money moves.

The **AI agents market is valued at** [$7.84 billion in 2025](https://www.marketsandmarkets.com/Market-Reports/ai-agents-market-15761548.html) and is projected to reach [$52.62 billion by 2030](https://www.marketsandmarkets.com/Market-Reports/ai-agents-market-15761548.html). [McKinsey](https://www.salesmate.io/blog/future-of-ai-agents/) estimates generative AI could add between $2.6 trillion and $4.4 trillion annually to global GDP.

And yet, these **agents are limited by structural flaws that prevent their full absorption into the financial world.**

**Paying for things is one of these.** Brian Armstrong [predicts](https://www.coindesk.com/tech/2026/03/18/the-protocol-ethereum-community-debates-foundation-s-new-mandate-document/) there will soon be more AI agents than humans making transactions on the internet. Despite how bold that sounds, agentic payments have been [largely speculative](https://www.galaxy.com/insights/research/x402-ai-agents-crypto-payments) in their early form.

The problem is structural and encompasses legal and technical constraints:

- **Proof of Personhood:** The entire architecture of traditional finance assumes users have real identities that can be verified through Know Your Customer (KYC), a requirement that doesn’t apply to AI agents.
- **Architecture for Humans:** Legacy financial systems were designed around humans and include settlement cycles, banking hours, geographic routing constraints, layers of intermediaries, and more, all of which limit the transactions an AI agent can perform.
- **Gated Access:** The financial infrastructure treats access itself as something to be granted. Products like prime brokerage, institutional custody, and derivatives clearing are simply unavailable to entities below a certain size.

This article touches on two main aspects of the agentic economy:

- How can we transition the current stack to make it agentic-first?
- Which network will be established as the mainstream infrastructure for agentic payments?

**The transition is already in process, with three converging standards:**

- One for **payments** (x402)
- One for **trust** (ERC-8004)
- One for **commerce**, that together form the first complete financial system designed for machines. (ERC-8183)

Few businesses are positioning themselves for this future, and the Ethereum ecosystem is one of them and the strongest candidate because of its censorship-resistant and secure nature.

What follows is a map of the infrastructure being built, the competitors racing to respond, and a deep dive into the tech stack, making EVM-compatible chains the primary candidate to become the settlement layer of the future trillion-dollar agentic economy.

# Chapter 2: Ethereum's Agentic Financial Stack

The transition to make blockchain networks agentic-first is already in progress.

Three EVM standards are converging into a complete, permissionless financial system for machines, covering the three important aspects of finance: Movement of money, trust, and the commerce lifecycle.

The crypto agentic sector went through its crest and trough, and it's currently trading at a [~$2.9 billion market capitalisation](https://www.coingecko.com/en/categories/ai-agents), down from a peak of $15-$20 billion.

While these numbers might look a little disappointing, the initial wave was mainly driven by speculation and the newness of this narrative. However, as always happens, tech takes some time to catch up. This is finally happening, with new standards like ERC-8004 gaining momentum. In terms of agent deployments, [over 98k have already been deployed via ERC-8004 across 10+ EVM chains](https://www.growthepie.com/quick-bites/eip-8004) since it went live at the end of January this year.

![Image](https://pbs.twimg.com/media/HGmExdNaoAAfr29?format=jpg&name=large)

Additionally, products like x402 from [@Coinbase](https://x.com/@Coinbase) have had a lifetime trading volume of over [$48 million](https://www.x402scan.com/) since their launch in May 2025, with peak volume in Q4 2025. These numbers plummeted as soon as they grew because users were speculating in the agentic economy, and multiple products gained traction they didn’t deserve in the first place. Now, when the numbers are a little more balanced, it reflects the real adoption metrics.

![Image](https://pbs.twimg.com/media/HGmE0aSaEAAHbJm?format=jpg&name=large)

In this section, we discuss three core standards or protocols that work together to make agent commerce possible at scale.

## x402: Payments

[x402](https://www.x402.org/), the **“internet payments standard”**, developed by Coinbase, revives the long-dormant HTTP 402 status code, reserved since the earliest days of the internet but never implemented. It **creates the payment infrastructure for machines** by embedding payment gates directly into web communication. Any server can require payment, and any client can pay in a single HTTP request-response cycle.

The mechanics are simple: A client requests a resource, and the server responds with HTTP 402 and payment instructions. Then, the client signs a stablecoin payment and resubmits. Afterwards, the facilitator settles onchain and the server delivers. There truly is no human in the loop. The [facilitator never custodies funds](https://www.galaxy.com/insights/research/x402-ai-agents-crypto-payments), but the agent authorises what to pay, and the facilitator handles how.

Since its May 2025 launch, x402 has processed [over 50 million transactions](https://www.coinbase.com/developer-platform/discover/launches/agentic-wallets). In December 2025, Coinbase [released V2](https://www.x402.org/writing/x402-v2-launch) with features like:

- **Wallet-based identity and reusable access sessions**, smoothing the user experience, providing benefits like lower latency, fewer round-trips, and cheaper repeated calls.
- **Modular architecture** makes the V2 a plug-and-play platform by clearly separating the protocol specification, its SDK implementation, and facilitators.
- **Unified Payment Interface** with multi-chain support, legacy payment rails like ACH, SEPA, or card networks.
- **Automatic discovery** enables the sellers to publish the APIs once, while facilitators stay synchronised without developer intervention.

Recently, x402 underwent an upgrade to [the Upto scheme](https://x.com/0xyoussea/status/2042286187956879447). While the older versions were good, it was running on a pay-per-request model, which isn’t ideal cause it requires knowing the cost upfront, which doesn’t work with LLMs, for example, with Upto, a client can authorise a maximum amount, and the server can settle for the actual amount used at the end of the request.

![Image](https://pbs.twimg.com/media/HGmE5B9bgAMh_Tf?format=jpg&name=large)

[Cloudflare](https://blog.cloudflare.com/x402/) co-launched the x402 Foundation and integrated it with its Agents SDK and MCP servers so AI agents can pay in batches, subscriptions, or daily rollups, ideal for things like “pay per crawl.” This is interesting because agents won’t need to settle immediately, and the batch transaction allows payment once all required data has been fetched. Moreover, cloud providers like [AWS](https://aws.amazon.com/blogs/industries/x402-and-agentic-commerce-redefining-autonomous-payments-in-financial-services/) demonstrate how to use services like Amazon Bedrock and CloudFront + Lambda@Edge to implement x402 payment flows, enabling agents and APIs to perform automated, pay-per-use USDC transactions over HTTP.

[Galaxy Research documented](https://www.galaxy.com/insights/research/x402-ai-agents-crypto-payments) that initial x402 activity was primarily speculative, with teams using the standard to mint and purchase memecoins, thereby driving transaction counts and volumes in late October, accounting for more than 50% of the volume until December 2025.

![Image](https://pbs.twimg.com/media/HGmE8qlbQAALqWW?format=jpg&name=large)

In the last few weeks, the average **transaction count has remained at ~200k**, **signalling that activity has now stabilised and that the organic adoption curve is forming,** with speculation no longer leading.

## ERC-8004: Trust

**x402 solves the payment problem, but the agents still have no way to know whether the counterparty is legitimate.** This is where [ERC-8004](https://eips.ethereum.org/EIPS/eip-8004) (went live on mainnet in late January) steps in. It **addresses the trust issue** by extending the Agent-to-Agent (A2A) protocol with a trust layer that allows participants to discover, choose, and interact with agents. ERC-8004 introduces three registries:

- The **Identity Registry** gives every agent a persistent onchain identity, an ERC-721 token with capabilities, endpoints, and trust models. It is similar to a KYC badge for machines, enabling any other agent to look it up, cryptographically verify ownership, and know exactly what they are dealing with before engaging in any real interaction.
- The **Reputation Registry** records cryptographically verified feedback after each interaction. Over time, this creates a performance history that accompanies agents, enabling other agents to decide whether to use their services.
- The **Validation Registry** coordinates third-party verification with economic stakes. It's a cryptographic or economic proof (ZK and TEE attestations) that an agent’s outputs are correct and not merely dependent on past clients’ ratings. This part of ERC-8004 is [currently not live and is in discussion with the TEE community](https://github.com/erc-8004/erc-8004-contracts#:~:text=The%20Validation%20Registry%20portion%20of%20the%20ERC%2D8004%20spec%20is%20still%20under%20active%20update%20and%20discussion%20with%20the%20TEE%20community.%20This%20section%20will%20be%20revised%20and%20expanded%20in%20a%20follow%2Dup%20spec%20update%20later%20this%20year.).

In terms of adoption metrics, it is live on 10+ EVM mainnet chains, with ~98k agent registrations; the largest number of ERC-8004-enabled agents is registered on [@Base](https://x.com/@Base), followed by [@Ethereum](https://x.com/@Ethereum) and [@MegaETH](https://x.com/@MegaETH).

![Image](https://pbs.twimg.com/media/HGmFBMjbEAACNbl?format=jpg&name=large)

## ERC-8183: Commerce

**There is a gap between payments and trust that neither x402 nor ERC-8004 closes on its own.** An **agent can pay and verify identity**, but **what happens if the work is never delivered**, the deliverable is wrong, or the provider disappears after receiving funds in a particular instance?

**In traditional commerce, this is handled by chargebacks, escrow, and dispute resolution, none of which exist natively onchain until** [ERC-8183](https://eips.ethereum.org/EIPS/eip-8183). Co-developed by [@virtuals\_io](https://x.com/@virtuals_io) protocol and the Ethereum Foundation's dAI team, ERC-8183 defines a single core primitive, [the Job](https://eips.ethereum.org/EIPS/eip-8183).

The Job is deliberately minimal. Three roles are involved: Client, which creates the job, defines the task, and may lock funds in an onchain escrow (depends on the implementation). The Provider submits a deliverable, typically a hash pointing to offchain content on IPFS or Arweave. The Evaluator evaluates the work done. For subjective work such as writing or design, an AI agent can be used to read the submission and compare it with the original requirements. For deterministic tasks like computation or proof verification, it can be a smart contract encapsulating a ZK verifier that automatically calls complete or reject. For high-value or high-risk work, a multi-sig wallet can be a part of the implementation. Every Job flows as:

- **Open**
- **Funded**
- **Submitted**
- **Terminal** (Completed, Rejected, or Expired).

As the [specification](https://eips.ethereum.org/EIPS/eip-8183) states: "A payment moves money. Commerce is everything around the payment that makes it trustworthy: what was agreed, whether the work was done, who verified it, and what happens if it was not." ERC-8183 also introduces **hooks**, optional smart contracts for bidding, reputation-gating, fund transfers, and privacy-preserving jobs. This is the onchain equivalent of the [authorisation-and-capture model](https://www.checkout.com/blog/authorize-and-capture) that makes card commerce possible, where the authorisation part is responsible for checking whether the client has sufficient funds, capturing the funds, and then transferring them to the merchant, thereby completing the transaction.

Each complete Job produces a verifiable onchain record of interaction, submission, and evaluation that feeds directly into ERC-8004 reputation registries, meaning commerce activity compounds into trust development, helping to attract more relevant work.

## The Loop

The three standards form a self-reinforcing cycle of commerce where the agents can be discovered through ERC-8004, and their previous work can be verified, and a new Job can be assigned based on that through following the ERC-8183 standard, giving more reviews for the agents and their work being verified, creating a loop that keeps on generating good work.

The first working demonstration of the full economic loop already exists. In early 2026, [a robot dog built by OpenMind plugged into a charging station and paid for its own electricity in USDC](https://circle.com/).

- OpenMind's OM1 operating system treated spending as a standard robot capability
- x402 handled payment negotiation over HTTP
- Circle's Nanopayments protocol batched thousands of offchain authorisations into single onchain settlements.

The robot did not need an account, a credit card, or a human. It signed an authorisation, and the payment was settled. Therefore, what appears as a concept is actually a working proof of concept.

The Ethereum Foundation has formally incorporated this infrastructure into its 2026 roadmap through the [dAI team](https://www.technology.org/2026/02/05/ethereums-decentralized-ai-revolution-surges-as-agentic-standards-transform-2026/), led by Davide Crapis, with the explicit goal of transforming Ethereum into a global settlement layer for AI.

# Chapter 3: The War of the (Paying) Machines

Recently, multiple competing visions for machine payments were launched, reflecting that the major industry players want to be part of this developing economy:

- [Visa released Visa CLI](https://en.cryptonomist.ch/2026/03/20/stablecoin-payments-visa-mastercard/), letting AI agents trigger card payments from a terminal without embedding or managing API keys.
- Stripe and Tempo [launched the Machine Payments Protocol](https://fortune.com/2026/03/18/stripe-tempo-paradigm-mpp-ai-payments-protocol/) alongside Tempo's [mainnet](https://www.coindesk.com/tech/2026/03/18/stripe-led-payments-blockchain-tempo-goes-live-with-protocol-for-ai-agents), a privacy-enabled payments-focused L1. Its co-founder, Matt Huang (Paradigm managing partner and Stripe board member), [told Fortune](https://fortune.com/2026/03/18/stripe-tempo-paradigm-mpp-ai-payments-protocol/) that agentic payments are still very early. Launch partners include Anthropic, OpenAI, DoorDash, Shopify, Revolut, and **both Visa and Mastercard.** The card networks are collaborating with the infrastructure that challenges them.

While there are many competing offerings, some of them work in [complementary ways](https://www.galaxy.com/insights/research/x402-ai-agents-crypto-payments), such as **x402 and Stripe Agent Commerce Protocol (ACP)**. **x402** is a standard for payments between software, best for use cases like API calls, data feeds, LLM interaction, and many more **cross-software interactions**. Stripe’s **ACP is more relevant in e-commerce**, enabling AI agents to purchase items from merchants without removing core requirements such as fraud detection, dispute resolution, refunds, regulatory compliance, and customer support. **They do this through Shared Payment Tokens (SPTs),** which provide merchants with [limited authorisation to charge a payment via their preferred infrastructure](https://www.galaxy.com/insights/research/x402-ai-agents-crypto-payments).

[Galaxy illustrates how they can work together with a travel agent example](https://www.galaxy.com/insights/research/x402-ai-agents-crypto-payments): **x402 pays for weather and airfare APIs**, and **ACP handles the flight booking** (regulated, human-approved). **ERC-8183 addresses the gap between them by providing an escrow-and-evaluator model** that is a programmatic replacement for chargebacks.

Even with many products being built in the agent payments category, products using the onchain rails will prevail because they are cheaper than card providers like Visa and Mastercard. In February, [Citrini Research](https://en.cryptonomist.ch/2026/03/20/stablecoin-payments-visa-mastercard/) crystallised the structural argument: AI agents, programmed to minimise costs, will systematically avoid 2–3% interchange fees when stablecoin transactions on L2s cost fractions of a cent.

# Chapter 4: If onchain, then which chain?

If the agentic economy will transact on crypto rails, the question becomes: which crypto rails?

Ethereum is the largest smart-contract-enabled blockchain with deep liquidity and security. To address its scalability problem, many alternative L1s emerged, promising faster execution. The usual rooted assumption in crypto is that a newer, better chain will eventually gain decent market share and attract users. For agentic finance, that assumption might be wrong, and there are reasons why Ethereum and its L2s will hold great market share.

- **The first non-negotiable is security.** An agent managing a portfolio, executing trades, or holding funds in escrow on behalf of a client needs the most pristine settlement layer available. Ethereum's consensus layer has operated without a successful attack since launch. The [ERC-8004 singleton contract sits on Layer 1](https://phemex.com/blogs/erc-8004-machine-economy-agentfi-intent-centric-ux) because enterprise-grade agents require that level of economic security as their anchor, even as high-frequency consumer activity settles on L2 networks where fees are negligible.
- **The second is composability**. A trading agent does not operate in isolation. In a single transaction chain, it might interact with [Aave](https://aave.com/) for lending, [Uniswap](https://uniswap.org/) for swaps, [Chainlink](https://chain.link/) for price feeds, and [Morpho](https://morpho.org/) for yield optimisation. That depth of programmable financial infrastructure simply does not exist elsewhere.
- **The third is standards convergence**, which is the argument competitors will find hardest to replicate. [ERC-8004](https://eips.ethereum.org/EIPS/eip-8004), [ERC-8183](https://eips.ethereum.org/EIPS/eip-8183), [x402](https://www.x402.org/), [Google's Agent-to-Agent protocol](https://medium.com/coinmonks/erc-8004-a-trustless-extension-of-googles-a2a-protocol-for-on-chain-agents-b474cc422c9a), and the Model Context Protocol via [Cloudflare](https://blog.cloudflare.com/x402/) are all deployed on EVM-compatible infrastructure.

It reflects the choices of the institutions building the stack. Coinbase's entire x402 architecture runs on [Base](https://www.theblock.co/learn/391983/what-is-coinbases-x402-protocol), an Ethereum L2. The Ethereum Foundation's [dAI team](https://www.technology.org/2026/02/05/ethereums-decentralized-ai-revolution-surges-as-agentic-standards-transform-2026/) exists with the explicit mandate to make Ethereum the AI settlement layer. Crapis (lead dAI) estimate that within three to five years, [the majority of Ethereum traffic will come from machines](https://decrypt.co/337403/ai-future-ethereum-developers-banking-on-it). [Nethermind](https://www.nethermind.io/blog/verifiable-autonomy-building-ethereum-agentic-infrastructure), a core Ethereum infrastructure company, is building ChaosChain, a protocol for agentic accountability built around ERC-8004, A2A, and x402.

[@Solana](https://x.com/@Solana) is the obvious competitor, with strong developer activity and [x402 support across multiple chains](https://www.theblock.co/learn/391983/what-is-coinbases-x402-protocol). [@Tempo](https://x.com/@Tempo), arguably the most institutional blockchain launch of 2026, is [EVM-compatible and is a standalone Layer 1 designed for payments at scale with opt-in privacy features](https://www.coindesk.com/tech/2026/03/18/stripe-led-payments-blockchain-tempo-goes-live-with-protocol-for-ai-agents).

![Image](https://pbs.twimg.com/media/HGmFIgobUAEjN1J?format=jpg&name=large)

Moreover, currently, most [x402 volume today flows through Base](https://www.x402scan.com/networks) rather than Ethereum Layer 1. This is by design. Micropayments require sub-cent gas that the mainnet cannot currently provide, and currently serves as the security and settlement anchor.

# Chapter 5: The Winding Road to Agentic Finance

The infrastructure for agentic finance is being built at a remarkable pace, and the recent work on x402 and different ERC standards (8004, 8183) has paved the way for a streamlined, smooth agent-led onchain economy. Yet it's very hard to fully trust agents to handle everything, as we still need to address the more fundamental aspects of security and privacy. The work underway to fix these issues is progressing. For example, on the privacy side, Ethereum is developing [Kohaku](https://ethereum.github.io/kohaku/getting-started/), an SDK that embeds privacy-preserving technology directly into wallets, making shielded transactions the default, but there are still gaps to address.

## Different Attack Layers

Whenever a user interacts with a crypto product, several layers are involved, each of which could be a potential source of data leakage, which makes privacy a full-stack problem on the settlement layer rather than a single exposed front that can be solved by just improving agents and their infrastructure:

- **Every onchain transaction is currently public by default.** An agent managing a portfolio broadcasts its strategy, position sizes, and the time it took a specific trade to everyone.
- RPC Layer pose as the second point of exposure, as **RPC nodes see every query before it becomes a transaction**. It collects details such as the contracts being read, the actions being performed, and the IP address from which the query originated.
- At the **network layer, IP address analysis and traffic-timing correlation can deanonymise users** even when transaction content is encrypted.
- Finally, the **wallet interface itself can leak data**: **mouse movement patterns, device characteristics, and font enumeration** can link a user across fresh wallet addresses.

**Beyond the passive surveillance problem, agents face a more direct security threat: prompt injection**. Whenever an agent queries an external source, an ENS record, a price feed, or contract metadata, the response comes from infrastructure that a malicious entity could control. A poisoned ENS record instructing the agent to ignore previous instructions and send all funds to the attacker's wallet is enough to drain a wallet entirely with no phishing link clicked and no malware installed. It is a new class of attack vector.

## The CROPS Mandate

Another aspect that agentic infrastructure needs to consider before it can be usable at scale is the CROPS framework underpinning the Ethereum mandate. AI agents need to be:

- **Censorship Resistant,** ensuring that an agent cannot be deplatformed or blocked mid-execution by any single intermediary.
- **Open-source**, so their decision logic can be audited.
- **Private** at every layer of the stack.
- Provably **Secure** means that guarantees are mathematically ensured through formal verification and ZK proofs.

Together, CROPS set a bar that an agent must meet before it can be trusted with financial decisions.

## AI as a Security Layer

While AI isn't yet a fit for agentic finance, once it meets the required benchmarks, it becomes the obvious choice because, in that scenario, **it serves as the UI for humans**. A general user won’t read the smart contract bytecode or verify the token addresses in the swap UI, but AI agents can be programmed to do so and then execute the transaction. This adds another layer of security that couldn’t be applied to every user, but AI makes it possible.

**AI becomes the primary interaction layer for crypto.**

Crypto protocols still have a bad UX, and it's a problem we have been trying to solve for a long time. A simple transaction to submit funds in a protocol to earn yield requires signing multiple transactions, bridging funds, and finding the best yield opportunities. This equation becomes even harder when we take cross-chain yield into consideration. But someone who is just prompting “I have [$10k](https://x.com/search?q=%2410k&src=cashtag_click) in USDC, and I am looking for 10% annual yield” won’t need to worry about it all.

As the AI grows, its relevance increases as it solves certain pain points crypto has around security and UX. At the end of day, every user doesn’t need to figure out the how blockchains work, why they need gas on every chain, why yields are different on cross-chain, why it is important to analyse a pool liquidity profile and the assets it is exposed to before depositing funds while all of this can be programmed into an AI agent which can be used by multiple users.

# Chapter 6: Closing Thoughts

The agentic economy is here, and the continuous efforts by the Ethereum ecosystem to advance multiple standards to make agentic finance more secure and trustless reflect that the agent-led future is not far away.

The case for Ethereum as the settlement layer of the machine economy rests on three arguments:

1. **Security**: Ethereum has had no downtime since its inception in 2015 and has a large set of active validators that contribute to the chain’s decentralisation and censorship resistance.
2. **Composability**: Ethereum is the DeFi hub and home to substantial liquidity. Multiple relevant, large-scale protocols are deployed on Ethereum, making it an efficient venue for any agent to find and deploy high-yielding strategies.
3. **Standards Convergence**: x402 handles the movement of funds, ERC-8004 handles the trust layer, and ERC-8183 ensures work is delivered, all present in EVM-compatible infrastructure. And the stack is still being extended: [ERC‑8211](https://x.com/biconomy/status/2041516284635120108), published in April 2026 and co‑developed by Biconomy and the Ethereum Foundation, adds dynamic, constraint‑guarded execution that lets agents adapt multi‑step DeFi strategies to live onchain conditions in real time. Together, the four standards cover the full commercial lifecycle: identity, payment, commerce, and execution.

**But none of it is sufficient until we address security and privacy requirements and treat it as a full-stack problem**. Ethereum is on its way to solving these problems through its roadmap, and the [AI space is generally skewing towards open-source code](https://www.swfte.com/blog/open-source-ai-models-frontier-2026).

This is one of the most active areas within crypto: Visa, Mastercard, Stripe, and a new generation of payment-focused L1s and L2s are building parallel infrastructure that addresses the machine payments user case through different architectural choices, including routing agent payments through existing card rails, or building purpose-built chains optimised for payment throughput rather than general smart contract execution.

While the competition is growing, **Ethereum’s edge is unlikely to be replicated, given the combination of programmability, security, and an open ecosystem of composable standards that no single entity controls.** For the set of agentic finance that requires trustless settlements, geographic regulatory independence, and DeFi interactions, cross-border commerce, the permissionless and censorship-resistant prevails.

The most likely near-term outcome doesn’t include a single winner but multiple winners, as **L2s might** **be better for x402 payments where fees are negligible, and speed is adequate, while higher-value running relies on** human supervision and Ethereum serving as a security anchor for all of it. As Ethereum grows, it will become more private over time, and its transaction fees will decrease even further; both are part of the current roadmap leading to many agents using the L1 itself.

written by [@TradFiHater](https://x.com/TradFiHater) and [@noveleader](https://x.com/noveleader) ✍️

Every week for the last 3 years, we have shared our research for free, directly in your email. Not a subscriber yet? Let’s fix it:

[https://research.castlelabs.io/](https://research.castlelabs.io/)

If you are more of a Telegram person, you can read all of our research without the noise on our TG channel:

[https://t.me/castlelabsreads](https://t.me/castlelabsreads)