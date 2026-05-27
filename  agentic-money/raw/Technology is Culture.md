---
title: "Technology is Culture"
source: "https://writing.dragonfly.xyz/post/the-agentic-economy-will-be-massive-agentic-commerce-won-t"
author:
  - "[[Dragonfly]]"
published: 2026-03-22
created: 2026-05-03
description: "This is where our thinking lives. Raw research. Real takes. Comprehensive analysis across crypto, emerging technologies, markets, and policy from Dragonfly."
tags:
  - "clippings"
---
Whenever an emerging narrative enters the public discourse, the prevailing thesis gets reduced to its most memetic form. Intuitively, when no one can empirically prove what will happen, provocation is rewarded over nuance.

The recent discourse around “agentic commerce” has been no exception. The market has coalesced around some version of: agents are proliferating; agents will need to transact; agents can’t hold bank accounts but can hold wallets; card networks charge 2–3%; therefore, stablecoins win.

This chain of logic is flawed on many levels. Agents can hold bank accounts under FBO structures. Moreover, the 2–3% reflects credit and fraud risk, which blockchains don’t solve.

However, the debate around “which rails win?” is downstream of a prerequisite question that has largely been omitted from the discourse:

Will most agents even transact in the first place?

The agentic economy will be enormous. The share of those agents that transact will not.

## The Agentic Economy Will Look More Like an Org Chart Than a Marketplace

Fundamentally, AI is a technology that automates. It takes some task – searching, aggregating, synthesizing – and performs it more efficiently than a human would. Agents are an actionable derivative of this. Instead of simply returning an output, they execute an action.

The implicit assumption the entire agentic commerce thesis rests on is that execution necessitates expenditure. In other words, for the majority of agentic tasks, agents will need to spend money to autonomously procure external resources, pay for compute and data on a per-use basis, and interface with other agents as independent economic actors.

This is fundamentally inconsistent with how agents are likely adopted.

Broadly, agentic deployment fits into two categories: commercial agents deployed on behalf of businesses, and consumer agents that augment our personal lives. Neither is likely to transact autonomously – for different reasons.

## Commercial Agents Are the Logical Evolution of SaaS

A decent mental model for commercial agents is the logical evolution of SaaS. Instead of augmenting workflows, they replace them. And in the same way 95%+ of software spend is via businesses and governments, 95%+ of agentic use cases at scale will likely be deployed within similar organizations.

This is the first nuance the prevailing agentic commerce thesis misses: the lion’s share of agentic demand won’t be agents booking flights for consumers; it will be top-down deployment within businesses. And importantly, an agent that automates tasks within a closed organization is qualitatively different from an agent that operates as an independent economic actor.

Take a sales agent. It plugs into a CRM, researches prospects, drafts personalized outreach, and schedules follow-ups. It does not spend money autonomously. It does not interface with external agents across organizations. It takes a task – sales outreach – and automates it within a closed environment.

Intuitively, this repeats across nearly every organizational function. A finance agent reviews and reconciles expenses; an accounting agent books journal entries, reconciles accounts, and prepares statements; a legal agent scans contracts and surfaces exceptions; a coding agent writes code.

In almost every use case, the agent doesn’t spend, nor is given the ability to spend. It is deployed top-down within a controlled organizational environment with permissioned guardrails.

And in the event it does need to interface cross-organization and pay for its API calls or data, the cost probably won’t manifest as an autonomous agentic payment. Any per-use cost likely gets abstracted away by whoever is selling the software itself. This is how the enterprise software stack already works. Platform providers negotiate curated partnerships with data vendors, compute providers and other infrastructure partners, bundle access into the platform cost, and pass it through as a single aggregated line item.

And moreover, they can do this at unit economics no individual agent could replicate autonomously. Compute runs through reserved capacity agreements with AWS, Azure, or GCP. Model inference is priced under volume agreements with Anthropic, OpenAI, or Google. Data enrichment through providers like Bombora or Clearbit etc. It’s all pre-negotiated and abstracted away.

Said differently, the agent’s 40,000 API calls, model inferences, and data lookups don’t generate 40,000 payments. They generate one invoice. The granularity of consumption has never been the same thing as the granularity of settlement, and businesses will likely prefer to keep it that way.

## Consumer Agents Will Orchestrate, Not Spend

While commercial agents likely won’t transact autonomously because organizations won’t let them, consumer agents won’t transact autonomously because people won’t want them to.

Take a scenario agentic commerce bulls love to cite. You ask your agent to book a trip to Tokyo. It searches hundreds of hotels, cross-references reviews, checks your calendar, applies your preferences. It then simply books the room autonomously. You don’t have to do anything. Naturally, agentic commerce bulls then extrapolate this UX across nearly all consumer purchases from groceries to household purchases to clothing etc.

The problem is that preferences aren’t static. They are revealed through the act of choosing itself. When you book a hotel, you are not simply getting some accommodation at the lowest price. You are making a judgment that reflects mood, context, risk tolerance, and other qualitative inputs you didn’t know you had until you were looking at the options.

In practice, the agent will search, ask follow-up questions, and return options. You will look at pictures, ask about the neighborhood, maybe read a few reviews. And then you will choose and authorize the agent to pay via card details it already has access to. In other words, the agent is a research assistant, not an independent economic actor.

Beyond perhaps some predictable and recurring purchases, this UX will likely be consistent across nearly all consumer purchases for the exact reason that consumer decisions are rarely a function of just price. The entire consumer economy is built on product differentiation. Whether it’s clothing, hotels, household purchases, or groceries, there are countless qualitative inputs that go into a decision that, not only will agents fail to capture – more importantly, these inputs will come out of the discovery process itself.

Agents will be powerful orchestrators at the discovery layer, but they will hand things off to humans when it matters. Semantically, that is not agentic commerce, and it certainly doesn’t necessitate new payment rails.

## Where Crypto Rails Actually Win: Bottom-Up Agents

While collectively these two categories will likely represent 95%+ of agentic deployment over the next five years, there is a third worth acknowledging.

Over the past few months a new category of bottom-up agents has begun to emerge. Catalyzed by the OpenClaw phenomenon, these agents fall into a qualitatively different category. Unlike the aforementioned commercial and consumer agents, they are genuinely autonomous actors operating outside any organizational principal. These agents actually need to pay for things and do so at a granularity and frequency that makes human authorization infeasible. And although the economy of bottom-up agents is extremely small today, it will likely grow as emergent use cases no one could have predicted manifest.

It is therefore only within this extremely narrow context that there is a credible debate about whether crypto rails or card networks are the optimal substrate. And while everyone has indexed on the technical arguments for why crypto rails are superior, they likely win for a different reason in my view – permissionlessness.

Today, the reality is that neither rails are technically optimized for agentic commerce. While blockchains offer theoretically better unit economics for micropayments, they lack auth and risk scoring – which likely matters even more in an agentic future. Moreover, while instant settlement is often cited as a feature it simply means a fraudulent transaction settles instantly on-chain. Conversely, card networks hand have sophisticated fraud graphs and tokenized credentials that agents can inherit, but these were trained on human behavioral patterns and don’t map cleanly to autonomous agentic transactions. Further, for cross-border transactions, agents are handicapped by the settlement times of card networks.

Perhaps counterintuitively, the reason crypto rails likely serve as the default infrastructure for this subset of agents is because blockchains are open, permissionless and unencumbered by regulation.

This is the ultimate structural advantage. While I’m sure card network incumbents like Visa and Mastercard will continue to adapt with initiatives like Visa Intelligence Commerce and Mastercard’s AgentPay, they are still public companies with compliance obligations, onboarding requirements, and institutional counterparties. Blockchains have no such constraints. Anyone can build on them, any agent can transact on them and no one needs approval.

Intuitively, an emergent, experimental category will build where there is the least friction.

## The Rails Aren’t the Bottleneck, We Are

The longer-term question however is how quickly this experimentation compounds into something more consequential. The bottom-up agentic economy only grows into the hype when autonomous agentic organizations demonstrably outperform agent-augmented human organizations; not marginally, but decisively enough that the top-down human constraints on agents become a competitive liability. At that point, agents won’t simply automate human tasks within closed environments, but rather they will become the organization itself.

However, we are likely still quite far from this future. The bottleneck won’t be the technology. And it probably won’t be the payment rails that “weren’t engineered for machines”. It’s everything else that wasn’t built for an economy of autonomous agents: regulatory frameworks, institutional bureaucracy, legal structures, and the social inertia around human decision-making. These are far more consequential constraints than anything technically within the payments stack. And unfortunately none of them get resolved by a protocol upgrade.

The agentic economy will be enormous; most of it will be billed monthly.

\-----

*This publication represents the subjective views of the author and are not necessarily the views of Dragonfly or its affiliates. This publication is for general information and discussion purposes and is not general or personal investment advice.*