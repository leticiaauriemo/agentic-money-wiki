---
title: "Agentic payments memo"
source: "https://www.natural.co/blog/agentic-payments-memo"
author:
  - "[[Kahlil Lalji]]"
published: 2001-10-23
created: 2026-04-26
description: "When exploring what I wanted to work on next, I wrote this 15-page memo on agentic payments"
tags:
  - "clippings"
---
When I was exploring what I wanted to work on next, I wrote this 15-page memo on agentic payments to formalize some of my thoughts on the problem space, how I expected the market to evolve, and the opportunities I saw. Between writing and releasing it, there have been many market developments, but none of this writing has changed. This is the original memo we used to raise our seed round.

## Preface

Today, agents can negotiate trucking loads, hire contractors, manage procurement and sales, but the second money needs to move, the workflow breaks.

A human has to step in to execute the payment.

That’s a temporary state of the world. Within the next decade, I believe agents will programmatically move more transaction volume than any other category, period. The rails to make that happen though don’t yet exist. We’re building them.

Specifically, we’re creating the natural language layer that lets agents transact directly with businesses and with other agents, across any financial rail, starting with ACH. Over time, we’re consolidating the fragmented payment workflows owned by banks and mediated by legacy networks, making them machine-accessible from the ground up.

Entire industries are missing billions in value because they can’t close the loop on payments. Think logistics agents that can’t settle freight charges automatically, property management agents that can’t pay contractors in real time, or procurement agents that can’t finalize vendor payments without human intervention.

We’re giving them the protocol to do it, and once these rails exist, every agent-based workflow instantly becomes end-to-end autonomous.

This is a once-in-a-generation moment. Money movement has been effectively static for decades, and now it’s about to be rebuilt, not for humans, but for machines.

## Intro

The payments system has always been built around human-to-human interaction, whether for personal exchanges or on behalf of businesses. Account numbers, card numbers, payment portals, etc. are all designed to be usable and traceable back to a person existing within the financial system.

This works well today when humans are the dominant actor, but as the world transitions into an agentic future, where agents are responsible for a majority of global transaction volume, we’ll need to create a new way for agents to interact with consumers, businesses, and increasingly, other agents.

Agent-led payments introduces many new questions: what type of accounts do they transact against? Who’s liable for disputes on payments initiated by an agent? What’s the card auth loop equivalent for decision making? How do you keep the system low-latency so that payments can be a required step in API execution?

Today, agentic payments make up a payment volume that quickly rounds down to zero in the financial system. But like the transition from in-person to online payments that Stripe pioneered in 2010, the companies building agentic products today will, over the next decade, own a meaningful portion of all payment volume globally.

These companies need better payments infrastructure built around their workflows to support the new problems and opportunities that arise in an agentic world. Right now, there is an opportunity to re-invent the financial system to be faster, cheaper, and more global for these agent-led companies.

## Background

For simplicity’s sake, we’re going to consolidate everything down into two payment categories that are going to exist: commerce and labor. Commerce refers to transactions that mediate the exchange of goods and services - think Amazon, Target, Walmart, etc. And labor referring to payments for human work that would have been captured by a payroll provider: ADP, Gusto, Rippling, etc.

These two categories have different characteristics and requirements, but both share similar underlying challenges when it comes to transitioning the payment volume to autonomous systems.

It’s also important to define the types of agent interactions that do or will exist as these similarly have different requirements and unique constraints. Those payment flows are the following:

### A2A (Agent-to-agent)

Agent-to-agent payments mediate value exchange between two fully autonomous systems. A2A payments can occur in a commerce setting, e.g. consumer travel agent and booking agent on behalf of an airline, and in a labor setting, e.g. two specialized agents working together on the same mobile app, one that’s focused on design and one that’s focused on software development. While most people are focused on the former market, we’ll also explore the opportunities underexplored by the latter.

### A2B (Agent-to-business)

Similarly, an agent-to-business payments can occur when, either, an agent is making commerce payments, e.g. a personal shopping agent making a purchase with a legacy business payment processing system via a browser agent, or when agents are remitting payments to businesses for labor, e.g. a construction management agent hires an electrician to do new construction electrical wiring and has to remit a payment via ACH.

### A2C (Agent-to-consumer)

Agent-to-consumer payments can be understood as replacing a corollary peer-to-peer payment made today via Venmo or Zelle. Someone may give an agent access to manage their personal finances, and involved in that is the fulfillment of payments to other individuals for non-business purposes.

## The problems

Now that there’s some alignment on the categorical buckets of agentic transactions, and the specific payment interactions, let’s examine the problems that are created in this future:

### Traditional rails become costly and too slow

Traditional financial rails (credit, debit, ACH, etc.) are designed for transactions at the frequency and speed at which humans operate. Using a debit card to make a purchase at Whole Foods will involve a temporary hold from the issuer, 1-3 business days of clearing, and a non-trivial amount of risk to the acquirer. Making an ACH payment to another business may have an even longer delay and lacks visibility on the recipient’s end.

If you’re hiring a human today to build a website for you, there may be a back and forth conversation that happens over multiple emails over the course of a week. Further, the delivery of the work may take days or weeks. The human-to-human interaction is slow.

When much of the work that would have historically been done by a human is now replaced by agents, and the time to delivery is shrunk down from weeks to seconds or minutes, it’s imperative that the financial rails that mediate these interactions are real-time.

Imagine a world where you task a general purpose agent to do something as ambiguous as "build this website". In this world, there are sub-agents that are far better at each part of this request: design, engineering, product marketing, etc. This is already happening with multi-agent architecture. In this construct, the master agent becomes a router for a bunch of sub-requests that may end up getting owned by different agents, and therefore, different companies.

This poses a new challenge: how do agents remit payments to other agents or businesses for tasks that they cannot complete on their own? The agent needs access to a set of tools that it can call to verify the identity of the receiving agent, transact between known and unknown third-parties over whatever financial rail is most applicable, and log the transaction in a centralized place for auditing and reconciliation purposes.

Further, if the agent submits a request to a specific design-focused agent, and the total latency of that request is going to be <5 minutes, then you can imagine a world in which the value that is being exchanged in that request need to be verifiable in nearly real-time as the agent is going to return work that it wants to be compensated for. The existing financial infrastructure doesn’t address any of these problems.

### Dispute arbitration is unclear

Today, when a payment gets disputed there is a well-defined process for arbitrating the request and identifying who will hold the financial responsibility. Typically this means that the issuer, or the bank, is responsible for mediating disputes and in the interim will be responsible for making the customer whole, and then going to the acquirer, or merchant, to determine any liability that the merchant is required to pay.

When determining liability the financial system is basically looking to determine if the authorized individual did in fact make the payment, and if so, if the merchant followed the required security protocols. This process basically segments transactions into two main categories: payments made by the authorized user and payments not authorized by the customer.

However, when agents start acting autonomously on behalf of consumers or businesses there is the introduction of new questions regarding tracing responsibility and dispute management. The obvious one is: what happens when an agent goes rogue and starts making transactions out of the scope of its instructions? This feels more boundable, and so we’re going to ignore it for now. The much harder question to solve is: what happens when there is incongruence between the transaction that an agent makes and the "satisfaction" that the consumer or business has with that decision.

In an example, you task an agent with booking a flight. The agent chooses a flight with a 12 hour layover that has no refund available, when you would have preferred to fly direct. You as the bearer of this decision are unhappy with the outcome and would like to dispute the transaction. Who is responsible for meditating this outcome and is there liability that the payment provider holds, or are you responsible for the outcome of this decision as the executor of this agent?

### Identity is hard to manage

When a human is executing a transaction today there is some presumption that they’re going to use their best judgment to determine the legitimacy of the counter-party, and they’re largely going to be able to determine which vendors are trustworthy and which are not. When agents are transacting on behalf of consumers and businesses, there is much greater risk that the agent cannot determine, with the same level of certainty, that the counterparty it’s transacting with is legitimate.

Let’s first create a simple scenario: you task an agent with hiring someone to paint a house. If you give the agent access to the internet, then it can pick up some of the same cues that a human would use to gauge reliability of a service provider: number of reviews, completeness of internet presence, etc. This will lead to most agents defaulting to some concentrated subset of the total option pool, but this isn’t that different from the way that humans operate.

The more complex problem arises when agents are interacting purely programmatically over an MCP server or whatever medium develops over the next few years. Today, API calls are tightly bound. Meaning, when you build software the third-parties you interact with are defined and completely deterministic.

In the world that is created by non-deterministic agentic workflows, there is new complexity introduced by the unknowingness of an unbounded set of counterparties. There will need to be a new method of uniquely identifying that the provider on the other end of an agent's request is trustworthy and credible.

### Payments quickly become global

When looking for a provider for a request today, most frequently the work is going to be given to some domestic option. This is because of a multitude of reasons not limited to: language, convenience, and ease of settlement.

In an agentic future, the number of potential vendors to any given problem is not nearly as restricted because of the shared medium: tokens. So when an agent is tasked with something ambiguous like "write this code" or "complete these translations" the number of potential vendors is large and broadly global. The entities or individuals that fulfill these requests may be domestic, but they’re far more likely to be international than ever before for the aforementioned reasons.

When international payments become 10x or 100x more common than they are today, the necessity for payments to be occurring on standardized rails without long settlement times or large FX fees becomes increasingly more important.

For context, today a domestic ACH will likely cost you (or your originating bank) <$2 to complete. However, if you want to make the same payment, and the receiving bank is international because of the number of intermediaries, that payment may end up costing >$20.

This makes the margin of international options unbearable today, and when you assume that the international payment volume is going to increase between 1 and 3 orders of magnitude, then you quickly come to the conclusion that you need a low-cost low-latency way to transact internationally.

### Existing risk and payment controls break

Today, payment networks and banks determine legitimacy and credibility of transactions during the authorization loop of a card payment or the processing of an ACH request. As in, when a card is presented at POS there is somewhere on the order of ~3000ms for logic to be run to determine whether the attempted transaction is likely a legitimate one.

These controls are designed to catch fraudulent transactions by observing deviations from expected *human* behavior. For example, if you mostly transact at ~40 merchants in and around New York, for on average $50 per/transaction, and then you attempt to make a $8,000 purchase in Milwaukee then it’s far more statistically likely that your card has been stolen.

These problems are well understood because networks like Visa and MasterCard have billions of transactions to backtest, and humans generally operate in predictable patterns. When agents become primarily responsible for an increasing number of transactions, some of the patterns by which they transact will feel human-esque, but many of the ways they transact will not as they are optimized around slightly different reward functions.

This will mean new datasets, unique fraud vectors, and challenges unforeseen.

### The internet revolves around human-entry

Because humans have been the "agent" by which most financial transactions occur, the UX that mediates those payments is inherently built to support human operation. Think entry fields on a website that are designed for a keyboard and mouse. This paradigm makes sense for the world as it exists today.

However, in an agent-led economy the need for human readable and interactable elements on a website is basically none. If you’re going to the extreme end of the argument and posit that you’re going to command an agent to make all of your purchasing actions, and you were going to create payments infrastructure from first principles to support this then you wouldn’t create a checkout experience as it exists today. Instead, you may conduct all transactions programmatically between an issuing and acquiring agent.

## The opportunities

It’s clear that today AI and agents are starting to make the jobs of workers, at least, more efficient. There’s a debate about the degree of job displacement that occurs from the shifts in AI, but I don’t think it’s unfair to make the judgement that a lot of work that’s done today by humans will at some point be done by AI.

The labor market is big. In 2021, "taxpayers filed 153.6 million tax returns, reported earning more than $14.7 trillion in adjusted gross income (AGI)" as reported by the [Tax Foundation](https://taxfoundation.org/data/all/federal/latest-federal-income-tax-data-2024/). Further, ~$700b gets reported and moves between contractors and businesses/individuals in the US, as reported by 1099-NEC and 1099-K.

Today, all of this payment volume is captured by players like Rippling, Deel, Gusto, and ADP because it’s payroll. As work starts to move from human laborer to AI, we have to begin to ask the question, "what happens with the payroll volume that is displaced today and needs to be re-captured by software?". This is one of the first big opportunities for disruption in agentic payments.

### Controllable wallets

For reconciliation and risk management purposes, it makes most sense for agents to have access to an infinite number of controllable wallets for their payment volume. Founders may decide that they want the agent to transact against a subset of their company’s cash balance, and so the wallet needs to support JIT funding of the wallet so that there is enough liquidity to support various payments, but not enough to open the business to large financial liability.

However, in addition to the risk consideration, there’s another benefit to controllable wallets, which is logical grouping of transactions or allowing a large set of agents to transact against corollary wallets with individual controls with ease.

### Rules & controls

Developers will want access to some set of deterministic rules and controls, likely injected in a "system prompt" for the agent. These rules need to be able to handle spending limits, approved and/or blocked counterparties, human approval requirements, etc.

These rules need to be applicable at an organization level, wallet level, or transaction level. Meaning, the businesses might declare a global rule regarding which types of transactions are and are not allowed, they may decide to implement these controls at a wallet level controlling the flow of funds for one agent, or they may set individual transaction level controls.

### Authorization tools

As mentioned before, today the authorization process is owned by the card networks and issuing banks, and plays a crucial role in determining the validity of transaction, availability of funds, and risk of a counterparty. Today, billing for use of AI agents happens asynchronously at the end of the month either at a flat rate or by usage.

As agent workflows become more complex, there will be many use-cases where people want to transact against a counterparty in a synchronous way where payments are real-time. Meaning an agent has a task that it needs to complete, it calls another agent (owned by another company) saying, "can you complete this?", the counterparty agent responds with, "yes, this is the amount and the payment location", and the initiating agent will need to be able to remit a verifiable payment in real-time before the counter party agent completes the API request.

Today, when looking at credit rails the entire latency of this process at POS is under ~3000ms, and we’ll need similar rails that approve these real-time transactions for agents in similar or better latency.

### Observability and tracing

To allow agents and their human counterparts to come to better decisions and improvements regarding payment flows, decision and event tracing and observability tools need to support both the non-deterministic and deterministic outcomes of agentic payments. Monitoring requests, outcomes, and support back testing of transaction decisions.

### Other payment types

Agents need to be able to transact over any preferred rail given the variable nature of counterparty preference. If paying a business that operates entirely on ACH the agent should be able to remit to the necessary account if needed. While stablecoins provide a low-cost, low-latency method of transacting between wallets, a fully functional solution should provide agents the option to choose the best payment method for a given transaction.

## Existing Players

### Redacted

Focused on outcome based pricing to capture greater incremental value for the work that agents do. While this is the right general sentiment (agent builders should be deriving more value than a seat-based or usage-based model), not building generalizable payments infrastructure to support any payment method is shortsighted.

### Redacted

Started as a tool to allow agents to hire humans to complete tasks that they were not able to complete on their own before changing focus to work on infrastructure to allow agents to move money.

### Redacted

Redacted is working on developing "the first fully regulated AI-native financial institution (FI) designed to serve the unique needs of the emerging AI economy."

### Redacted

Enabling fast, secure, and compliant card payments for AI-driven transactions.

### Redacted

Redacted empowers AI agents to conduct transactions effortlessly. They can pay businesses, verify their identity, and access essential data and services in real-time.

### Redacted

Redacted is powering agentic card-based payments. Users connect a card to the Redacted wallet and agents have the ability to transact against that wallet. This requires both agent and consumer adoption in order to execute the payment.

### Redacted

Redacted is building virtual cards you can give AI Agents like OpenAI Operator, and more. They issue unique cards for each transaction, and give you spending controls to manage how your agent spends.

## Distribution

There are three distribution strategies to take advantage of when considering building in agentic payments.

### Y Combinator

Similarly to Stripe’s early days. Many of YC’s new cohorts are highly focused on AI and agentic use-cases. Sampling the past 4 batches you’ll find that 80%+ of the batches are entirely AI focused products or building around AI in a meaningful way.

While these companies are, in absolute terms, small today. They will at some point be large companies that account for tens of billions of dollars in enterprise value.

From my conversations with dozens of agent-focused YC founders, it’s clear that there isn’t yet a clear solution for handling some of these agentic payment flows. As the general agentic infrastructure progresses over the next 12 to 24 months, these founders will need to be able to turn to a provider to offer the infrastructure that supports their workflows, and this is an opportunity that needs to be capitalized on now.

### PayPal-esque

If doing one-way remittance of payments to businesses it’s feasible that an effective method for increasing network adoption is to push funds from one stablecoin wallet to another in the businesses' name that they can KYB into and pull down from at their own convenience.

Similar to the PayPal growth strategy, if you own the account that the funds are originating from and have the ability to ledger a unique receiving account, then you can minimize transaction fees and increase the number of parties on the network because recipients are highly incentivized to sign up in order to claim funds.

In the case of agentic payments, the flow of funds might look something like: there is an agent that is responsible for scheduling, coordinating, and paying out a bunch of contractors to work on a new construction project. The agent has 1) the amount it needs to pay these contractors and 2) the business's name. It can make a stablecoin payment from its wallet to one in the business's name, and the contractor will receive an email saying that they need to complete KYB in order to withdraw the funds from the wallet.

This allows the agent to transact in real-time without having to worry about counterparty opt-in, reconciling account and routing information, or managing the KYB status of the business.

### AP/AR as wedge

Another valid wedge into agentic payments is to use the already existing workflows found in AP/AR.

Today, in early-stage companies the founder or bookkeeper will spend a lot of time tracking invoices they’re sent over email, copying payment details, and scheduling payments for remittance. It’s an incredibly manual process prone to error. A study found that, "86% of small and medium-sized businesses manually enter invoice data, increasing inefficiencies and error risks".

This problem is even more acute with larger companies where there are so many external vendors that it’s hard for companies to keep track of all the invoices being received and their purpose. There was a case a few years ago where someone pled guilty for, "scamming Facebook and Google out of more than $100 million. Impersonating a company with whom both tech giants do business, Rimasauskas sent fake phishing emails containing forged invoices and convinced the companies to wire funds to bank accounts he controlled".

This process is an unavoidable part of the finance process, and ripe for disruption with agents. Each part of this process is solvable today, OCR for document or pdf parsing to pull out the data, an optional human-in-the-loop approval step, and controllable wallets for an agent to execute the transaction.

It’s an automation with immediate value to companies today, however, the infrastructure built to support these workflows sets you up to tackle the much larger problem which is generalizable payment rails for agents to transact.

## Risks

When looking at this market, there are two risks that hold real merit. The first, is that the agent market doesn’t mature fast enough, and the second is that the existing solutions are sufficiently good such that a new payments infrastructure layer is not needed.

### Market maturity

Today, most agent-led startups are building their entire workflows internally. Regardless of the number of steps the agent is completing, the relation of workflow requirements to the core business, or the relative value of required steps, the entire agentic process is largely owned internally.

While this is a fine interim solution, we have to imagine that in the near future there will be a meaningful amount of specialization in the creation of agents. Meaning, a company may set out to create an agent that accomplishes a broad task say, "managing a warehouse", but within are going to be companies that own each portion of that process (scheduling, maintenance, security, hiring, etc) in a more effective way than if one company is responsible for a number of highly specialized tasks. This can be understood as agent interoperability.

The lack of specialization in agentic workflows and progression in agent interoperability means that the market for agent to agent payments has also not yet materialized. In a world where there are highly specialized agents that are owned by different companies, the necessity to transact between agents in real-time becomes a P0 technical problem, but until that’s the reality of the agentic landscape A2A payments are basically non-existent.

Further, today most agentic products that companies are building stop short before they get to any payment execution. Take [Avery](https://callavery.com/) as an example who is working on management of multi-family buildings. Scheduling and coordinating maintenance requests is a core part of their workflow, however, when it comes to payment remittance they still rely on property managers to manually send payments because there isn’t a simple and reliable way for them to introduce a payment step in their agent’s workflow.

With the rate of development of the agentic landscape I find that the real risk in this point is missing the wave of how agentic interoperability actually materializes, and not in the market failing to reach maturity.

### Existing solutions

The second risk when exploring agentic payments is that the existing solutions, most notably Stripe, come to solutions that are good enough that people build their workflows around those solutions.

If you look today at Stripe’s early agent toolkit, you’ll notice that most of the functionality is built around agents interacting with the internal Stripe APIs (creating products, updating subscriptions, creating invoices) or things that humans would have done on the Stripe dashboard.

![Stripe APIs](https://www.natural.co/assets/images/blog/agentic-payments-memo/stripe-apis.jpg)  
While these are helpful features, as Stripe’s product is quite large and complex at this point, the main functionality that we’re positing will need to exist is focused on the execution of payments.

There is a developer preview of an API that gives agents access to programmatic provisioning of single-use cards for purchases, and while helpful this commerce use case only represents a fraction of the payment volume that will be agentically driven in the near future.

![Stripe Developer Preview](https://www.natural.co/assets/images/blog/agentic-payments-memo/stripe-developer-preview.jpg)  
If you believe that most transaction volume will eventually shift away from humans and towards autonomous systems then you come to the conclusion that you need to build purposefully around that and that only.

## Additional reading

Sendbird. (2024, May 7). *AI Agent-to-Agent Economy: What is it and Why Does it Matter?* [https://sendbird.com/blog/ai-agent-to-agent-economy](https://sendbird.com/blog/ai-agent-to-agent-economy)

Nevermined. (2024, May 14). *Payment Options for AI Agents: Comparing Stripe & Nevermined*. [https://medium.com/nevermined-io/payment-options-for-ai-agents-comparing-stripe-nevermined-f6ca0b82e1d7](https://medium.com/nevermined-io/payment-options-for-ai-agents-comparing-stripe-nevermined-f6ca0b82e1d7)

Stripe. (n.d.). *Agents Documentation*.  
[https://docs.stripe.com/agents](https://docs.stripe.com/agents)

Google Developers. (2024, May 14). *A2A: A New Era of Agent Interoperability*. [https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/](https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/)

Fintech Brainfood. (2024, May 26). *Four Models: Agentic Payments*. [https://www.fintechbrainfood.com/p/four-models-agentic-payments](https://www.fintechbrainfood.com/p/four-models-agentic-payments)

The FR. (2024, May 29). *Agentic Payments: The Essential Foundation for Agentic Commerce*. [https://thefr.com/news/agentic-payments-the-essential-foundation-for-agentic-commerce](https://thefr.com/news/agentic-payments-the-essential-foundation-for-agentic-commerce)

Stripe Developers. (2024, May 13). *Adding Payments to Your Agentic Workflows*. [https://stripe.dev/blog/adding-payments-to-your-agentic-workflows](https://stripe.dev/blog/adding-payments-to-your-agentic-workflows)

Crossmint. (n.d.). *AI Agents Solutions*.  
[https://www.crossmint.com/solutions/ai-agents](https://www.crossmint.com/solutions/ai-agents)