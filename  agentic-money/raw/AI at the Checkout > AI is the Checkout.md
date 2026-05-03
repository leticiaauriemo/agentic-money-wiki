---
title: "AI at the Checkout > AI is the Checkout"
source: "https://x.com/sytaylor/status/2050906143044641149?s=46"
author:
  - "[[@sytaylor]]"
published: 2026-05-03
created: 2026-05-03
description: "The merchants are trying to tell you something.After two years of agent demos, chatbot checkouts, press releases, and “AI shopping” theatre,..."
tags:
  - "clippings"
---
![Image](https://pbs.twimg.com/media/HHUQwnEXoAAjO8Z?format=jpg&name=large)

The merchants are trying to tell you something.

After two years of agent demos, chatbot checkouts, press releases, and “AI shopping” theatre, the market has found its first real answer.

The AI does not own the checkout.

The merchant does.

On April 24, 2026, Amazon, Meta, Microsoft, Salesforce, and Stripe joined the [Universal Commerce Protocol (UCP) Tech Council](https://www.newsfilecorp.com/release/294133/Amazon-Meta-Microsoft-Salesforce-and-Stripe-Join-the-Universal-Commerce-Protocol-Tech-Council).

They sit alongside Google, Shopify, Etsy, Target, and Wayfair.

**That is every hyperscaler. Every major commerce platform. Every payments network of relevance in the transatlantic sphere**. The card schemes (Visa, Mastercard, Amex), the PSPs (Stripe, Adyen, Checkout), the marketplaces (Etsy, Wayfair, Target, Walmart, Best Buy, Home Depot, Macy's, Flipkart, Zalando) — all on the same protocol.

**This is the first time the agentic commerce category has agreed on** **anything**.

It’s now clear.

**The chatbot does not own the checkout. The merchant does.**

The best metaphor is the shipping container.

Before containers, global trade existed, but every handoff was bespoke. Ports, ships, warehouses and merchants all had their own weird little workflows. Commerce moved, but it dragged.

The container standardized the interface.

It did not own the goods. It did not replace the merchant. It made the whole system interoperable.

UCP is the container for agentic commerce.

## What is UCP, and why does it matter?

The Universal Commerce Protocol (UCP) is an open standard designed for **agentic commerce**. It acts as a "common language," allowing AI agents (like Gemini or ChatGPT) to interact directly with merchant backends without the user ever visiting a website.

- **Discovery:** Agents query a merchant’s /.well-known/ucp manifest to dynamically discover capabilities like loyalty programs, pre-orders, and product catalogs.
- **Negotiation:** AI and the merchant backend negotiate real-time pricing, tax, and complex discount stacking via standardized APIs.
- **Transaction:** Secure, API-driven checkout sessions finalize the sale, often utilizing the **Agent Payments Protocol (AP2)** for verified, one-tap payments (e.g., Google Pay, Shop Pay).
- **Fulfillment & Settlement:** UCP orchestrates logistics (shipping vs. pickup) and provides post-purchase status updates directly to the agent.

UCP is not a payment protocol. Commerce is everything before and after the transaction. When I [mapped the agentic payments landscape in January](https://www.fintechbrainfood.com/p/the-agentic-payments-map) the protocols broke down into layers.

You’ll note Google has several layers in sync:

- **Agent communication layer** — how do agents talk to each other? (A2A)
- **Mandate layer** — does the agent have authority to pay? (AP2)
- **Transaction layer** — what's being bought, and how does the checkout work? (UCP)

The payment itself still goes through the traditional rails like cards, ACH, stablecoins etc. That’s one of the things that makes agentic commerce so confusing. Not every protocol is trying to do the same thing.

And even in the transaction coordination layer, there’s complexity. MPP and x402 are designed for agents buying online resources (API access, etc.), ACP and UCP are about commerce, how do consumers find, select, and pay for goods and services online.

**The core difference between UCP and ACP is who they face.**

- **UCP: The Merchant owns the checkout.** UCP was [co-developed by Google and Shopify](https://shopify.engineering/ucp), Merchants own the cart. Merchants own the checkout. Merchants remain the merchant of record. **The agent is the discovery surface, not the storefront.**
- **ACP, OpenAI's competing standard, started from the opposite end of the funnel. It began with checkout — Instant Checkout inside ChatGPT** — and worked outward toward discovery and fulfilment.

UCP started with the full commerce flow and worked inward to the details. Today the two specs are converging. The difference is the path each took to get there, and which one had the architecture coalitions could trust early

**UCP's other clever move was being deliberately layered.**

Like TCP/IP, it separates concerns.

- Core checkout primitives sit at the bottom.
- Capabilities (Catalog, Orders, Checkout) sit above.
- Extensions (loyalty, fulfillment, subscriptions) compose on top.

Merchants implement only what they need, and can make it work with any payment method or loyalty integration. As long as they own the [namespace](https://en.wikipedia.org/wiki/Domain_Name_System) (the .com or equivalent that they’re impacting), they can do what they like with the workflow and protocol.

(That's why every PSP, every commerce platform, and every hyperscaler eventually converged on it. The architecture lets them all extend the protocol without permission.)

The combination of

1. A coherent stack from communication to consent to commerce
2. Being merchant-initiated and owned

Has made UCP an early winner, and a center of gravity for the agentic commerce conversation. There may yet be merit in the “checkout in the LLM” model that ACP was designed for, but it doesn’t yet have traction.

If you’re building a standard, job 1 is to get support for it. And UCP now has that.

The bigger question is if everyone supports it, will it make any difference?

## Is agentic commerce working yet?

The data is mixed.

**All the predictions say agentic commerce is the next big thing.**

- [McKinsey](https://www.mckinsey.com/industries/retail/our-insights) says agentic commerce is a $3-5 trillion category by 2030.- [Morgan Stanley](https://www.morganstanley.com/) says $190-385 billion in US e-commerce by 2030 — roughly 10-20% of online retail.

But I can't find evidence that customers are adopting this en masse. Maybe they are. Maybe it's just early. But it’s not hitting the mainstream.

**The mainstream is not here yet.**

In October 2025, Maximilian Kaiser (University of Hamburg) and Christian Schulze (Frankfurt School of Finance) published [the first peer-reviewed study](https://ssrn.com/abstract=5585812) of LLM e-commerce traffic. They took 12 months of first-party data from 973 e-commerce sites and 50,000 ChatGPT-referred transactions compared against 164 million traditional-channel transactions.

The findings:

- ChatGPT referrals underperformed every traditional channel except paid social
- Affiliate links converted 86% better than ChatGPT
- Organic search converted ~13% better than ChatGPT
- ChatGPT accounted for 0.2% of total traffic across the dataset
- The authors concluded parity with organic search inside a year is "unlikely."

**But the early adopters are showing promising signs.**

- **Attribution:** [Adobe says](https://business.adobe.com/blog/ai-driven-traffic-surges-across-industries) AI-driven traffic to retail is up 693% YoY for the 2025 holiday season — and for the first time, AI referrals are converting 31% better than other channels (vs. 9% worse just three months earlier)."
- **Attribution:** Shopify says [AI-attributed orders grew 15x](https://seekingalpha.com/news/4550530-shopify-outlines-ai-driven-commerce-expansion-as-company-targets-low-30-percent-revenue) since the start of 2025 — that's the freshest number from their Q4 2026 earnings call."
- **AI gives higher conversion:** [Panxo says](https://www.panxo.com/blog/agentic-commerce-chatgpt-conversion-rates-outperform-every-channel) ChatGPT converts at 11.4%, beating direct, paid search, organic, email, display, and social.

Two things are true at the same time. AI-referred traffic is growing fast off a tiny base, and the mainstream isn’t here yet.

And that’s OK.

Most people use AI as a better google, that’s showing up in attribution and marketing data, but the conversion jury is still out.

The early adopter merchants are trialling agentic commerce

![Image](https://pbs.twimg.com/media/HHURI2OXsAEY6gV?format=jpg&name=large)

Except in one specific place. Where merchants own the AI, the data isn't mixed at all.

## Merchant-owned won because it converts

When I wrote [The Checkout is Dead](https://claude.ai/chat/LINK) almost a year ago, ChatGPT had just integrated checkout into its interface. Perplexity and others followed. The obvious question was, how is this going to fly?

Merchants risked losing the customer, losing the data that helped convert them, and losing the signals that flagged fraud. The LLM-as-a-channel approach meant ceding much of the customer relationship and potentially paying some unknown take rate (ChatGPT wanted to charge 2% initially).

Every one of those concerns was real. None of them mattered. Because the only thing that needed to be true for the model to work was that conversion was good.

Narrator: The conversion was not good.

**Walmart tested 200,000 SKUs through ChatGPT Instant Checkout.** Daniel Danker, Walmart's EVP of AI Acceleration, Product and Design, [told WIRED](https://www.wired.com/story/ai-lab-walmart-openai-shaking-up-agentic-shopping-deal/) the conversion was one third of click-out rates. He called the experience "unsatisfying." [Two weeks later, OpenAI announced the closure of Instant Checkou](https://www.retaildive.com/news/walmart-sparky-chatgpt-instant-checkout/815647/)t — the agent-owned-checkout implementation. ACP itself moved on, evolving toward the merchant-owned model the spec now supports.

**Walmart then ran the experiment the other way**. They embedded their own assistant — Sparky inside their app (and later as a ChatGPT app), but kept cart, login, and checkout on [Walmart.com](https://walmart.com/).

![Image](https://pbs.twimg.com/media/HHURSSjWgAAc1ie?format=jpg&name=large)

Agentic Commerce in chatbots do not convert as well as owned websites

The results from Walmart's [Q4 FY26 earnings call](https://www.investing.com/news/transcripts/earnings-call-transcript-walmart-q4-2026-beats-eps-forecast-stock-rises-93CH-4513893):

- Half of Walmart's app users have engaged with Sparky
- Sparky users have an average order value 35% higher than non-Sparky users
- Sparky inside ChatGPT converts at roughly 70% of [Walmart.com](https://walmart.com/) direct rates — more than double ChatGPT Instant Checkout's run rate (but not quite as good as the owned channel)

**This is the experiment the entire industry needed someone with Walmart's scale and leverage to run.**

The control group is the website itself, and the website is still winning, but I don’t think that lasts. Those 1,000s of tiny micro optimizations will come to Sparky.

Walmart didn't use UCP — their experiments predate it. But they ran UCP's hypothesis as a controlled test on the largest retail surface in the world and disclosed the results on an earnings call.

And it's not just Walmart. Tatcha (Unilever-owned luxury skincare) attributes [11.4% of total site revenue](https://alhena.ai/case-studies/tatcha) to its on-site AI assistant, with conversion 3x site average and AOV up 38%. Microsoft Copilot Checkout reports 53% more purchases within 30 minutes when shopping intent is present. The pattern is consistent across every dataset where the merchant owns the AI:

**AI by the merchant can work. AI by the aggregator doesn't yet.**

There are still some questions the industry will need to work through like:

- **Is fraud worse or better with agentic commerce?** I can’t find any data on this, and it could go either way. Apple Pay is proud of reducing overall fraud in e-commerce vs other payment methods; agentic commerce could go that way. But fraudsters are always the earliest adopters and will exploit any weak spot.
- **Are returns worse or better with agentic commerce?** We just don't know — agentic transaction volumes are still too small for return-rate signals to be statistically meaningful. But if your agent yolo bought a bunch of stuff for you, are you gonna hit that chargeback button or are you liable? [Target thinks you’re liable](https://www.businessinsider.com/targets-google-gemini-ai-shop-terms-update-2026-3). The schemes are still building their frameworks.
- **How will attribution work?** ACP and UCP webhooks tell merchants what sold and which agent sold it. They tell merchants nothing about discovery, consideration, or whether the sale was incremental versus cannibalized. Retail media networks are about to get very confused.

A lot of this will get solved at the payment network layer, as card networks build their liability frameworks and security models around trusted agents and update how payments work accordingly.

## We're early. We're experimenting. And the cost of trying has never been lower.

When Apple Pay launched, it was optional. Today, it's [around 14% of US online payments](https://capitaloneshopping.com/research/apple-pay-statistics/), and on mobile, it's table stakes.

AI adoption is near-universal, but AI value capture is still concentrated in a small minority. Like everything in AI, the 1% are getting incredible gains. Most people are using it as a better Google search.

**The danger here is complacency.**

When the early-adopter crowd is rushing into something and getting value from it, that's your signal to pay attention. These are businesses reacting to actual customer demand.

What the early adopters are doing today will be universal in 10 years.

**And it has never been cheaper to experiment or build.**

With agentic coding, tooling, and workflows, experiments that used to take months and large teams can be cranked out much faster and at lower cost (assuming your production back end is capable of running experiments and A/B tests).

If merchants get this right, the cost of trying a new checkout flow, a new merchant agent, a new AEO experiment, has gone from six engineers and a quarter to one engineer and an afternoon. That changes the calculation.

The merchants who get this will run twenty UCP experiments in 2026. The merchants who don't will run one in 2027, when the data is already in, and the option is already expensive

(See the [Enterprise AI Playbook](https://www.fintechbrainfood.com/p/ramp-cracked-ai) from a couple of weeks ago for pointers on how).

**The longer-term question becomes: how do you optimize conversion with AI assistance?**

Merchant AI starts with answering questions, building trust, and suggesting upsells. Over time, merchants, AI labs, and everyone else will optimize the conversion, and as that happens, I fully expect AI conversion to outpace existing e-com checkout conversion.

If you buy that hypothesis, then you need to be:

- Discoverable to agents
- Able to build agent-friendly checkouts
- Ready to communicate (merchant-side AI)
- Ready to optimize that experience over time

The merchants who win will run AI on both sides. A consumer agent for discovery. A merchant agent for conversion. UCP is what lets them talk to each other.

## Don't treat AI as just another marketing channel.

Do get UCP-ready. The cost is real but bounded. Being on the wrong side of the next 18 months could be the difference between a great holiday season and being the next category to get SaaSpoacalypse’d.

Nobody knows exactly when this hits.

But the probability of it being an "if" is low.

When your downside is limited.

When your upside is unlimited.

When the cost of trying something new has never been cheaper

The gap between you and experimentation should be zero.

ST.