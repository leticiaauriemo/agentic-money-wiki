---
title: "🧠 How Commerce is Being Reinvented for Agentic AI"
source: "https://www.fintechbrainfood.com/p/commerce-for-ai"
author:
  - "[[Simon Taylor]]"
published: 2026-05-24
created: 2026-05-27
description: "How agentic AI is reimagining commerce: discovery, checkout, authorization & fulfillment. And the 5 levels of self-driving shopping experience."
tags:
  - "clippings"
---
Discovery, referral, policy, cart building, authorization, and fulfillment, are all being reimagined and reinvented. Plus; Google's Universal Cart, The Fintech Executive Order and Mercury's $500m Series D.

<audio controls=""><source src="https://beehiiv-publication-files.s3.amazonaws.com/uploads/tts_files/d96f71aa-ab16-4291-b408-729b925e0802/fd020496-18a7-4bc6-bf88-b9e05635821f.mp3?X-Amz-Algorithm=AWS4-HMAC-SHA256&amp;X-Amz-Credential=AKIAQCMHTQSE2JGAGXHJ%2F20260527%2Fus-east-1%2Fs3%2Faws4_request&amp;X-Amz-Date=20260527T182655Z&amp;X-Amz-Expires=604800&amp;X-Amz-SignedHeaders=host&amp;X-Amz-Signature=3e21fa1650b67f607283f67b3b499c01758a539af236b9517b90fd6459a555ba" type="audio/mpeg"> Your browser does not support the audio element.</audio>

### Weekly Rant 📣

### 🧠 Commerce is Being Reinvented for AI

*Whenever you hear about "agentic commerce," it's usually about payments. When in reality, commerce is about so much more than the payment. The stages of an e-commerce journey, like discovery, referral, policy, cart building, authorization, and fulfillment, are all being reimagined and reinvented to be AI native as we speak.*

There are a few core observations I wanted to flesh out.

1. There are many "commerce" lifecycle moments that AI is impacting today
2. Each step will become more agentic and autonomous over time
3. Right now, it's not a single straight-through process that's end-to-end autonomous
4. The entire process needs joining together to become fully autonomous
5. The impact of that will be an upending of how e-commerce works today

If you think about the 5 levels of autonomy in self-driving cars, Stripe had a [similar model for commerce](https://stripe.com/annual-updates/2025?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com). These levels are typically: **no automation**, **AI assistance**, **partial autonomy**, full autonomy in certain **conditions**, high **autonomy for some flows** (or geographies), and finally **full** autonomy for any payment anywhere, any time.

Now imagine each of those levels of autonomy could be different for each stage of the customer lifecycle. You'd then get this 2x2.

![](https://media.beehiiv.com/cdn-cgi/image/fit=scale-down,quality=80,format=auto,width=720,onerror=redirect/uploads/asset/file/3979c318-e4a6-443a-821b-037c1966311a/image.jpeg)

This week's Rant unpacks how we get to fully autonomous self-driving commerce.

### 1\. AI is Changing Commerce Experiences Today

It's mostly in marketing. But that's changing. Fast.

Commerce platforms like Shopify and WooCommerce are actively integrating AI and agentic capabilities to reinvent the earliest stages of the e-commerce lifecycle: discovery, referral, and attribution to prepare for a future where customer interactions are increasingly autonomous.

#### Discovery and Attribution: High impact today

**Discovery is already at Level 2**, agents are comparing thousands of SKUs without being asked **and pushing into Level 3**, where they auto-filter on learned preferences

To enable this, companies have focused on ensuring product catalogs can be found through conversational interfaces and AI recommendations. This means new features like:

- **AI-Powered Product Cataloging and Tagging:** Making products highly discoverable by generalized AI agents and search engines.
- **Using llms.txt files and** [**Schema.org**](https://schema.org/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) **markup** to make product data machine-readable. These files give AI crawlers a clear way to understand store content, similar to a sitemap for AI.
- **Optimizing for AI search (GEO):** meaning merchants can get better traffic. AI-driven orders increased significantly in Q1 2026.

From [AI at the checkout → AI the checkout.](https://www.fintechbrainfood.com/p/ai-checkout)

❝

- [During the 2025 holiday season](https://news.adobe.com/news/2026/01/adobe-holiday-shopping-season?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) — and AI referrals converted 31% better than other channels. By [March 2026, that conversion advantage hit 42%, a new record.](https://business.adobe.com/blog/ai-traffic-surge-retail-sites-not-machine-readable?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com)
- [Shopify's Q1 2026 earnings show AI-driven traffic to stores grew 8x YoY](https://www.theglobeandmail.com/investing/markets/stocks/SHOP/pressreleases/1716522/shopify-shop-q1-2026-earnings-transcript/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com), and orders from AI-powered searches increased nearly 13x. New buyer orders from AI arrive at nearly twice the rate of other channels.
- Traffic from Shopify's structured product catalog converts 2x better than traffic from general AI searches working off scraped or outdated data. **Structured data wins.**

[AI at the checkout → AI the checkout.](https://www.fintechbrainfood.com/p/ai-checkout)

#### Referral — High impact today

**Referral sits at L1 heading to L2**. The links carry context, but agents aren't yet choosing *which* referral path to take autonomously.

When you click a link inside your LLM or ask your agent to, the link now needs to carry a payload linking the AI citation to the merchant's site, with consent signals (like a cookie, saying you consented to the agent doing this). In [UCP](https://developers.google.com/merchant/ucp?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) it works like this:

- The LLM looks for a file at \[[merchant.com/.well-known/ucp](https://merchant.com/.well-known/ucp?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com)\]. This manifest tells the LLM what the store is capable of (e.g., guest checkout, identity linking, or loyalty points).
- The "link" carries a UCP Context Object. This tells the merchant site that the user didn't just stumble upon the page — they were sent by an agent with a specific Intent.

This introduces our first new step in the e-commerce lifecycle: **Intent**.

#### New: Intent

**Intent is L1 at best.** AP2 mandates exist in spec, but live implementations are thin.

Google's [AP2 protocol](https://ucp.dev/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) (and increasingly many of the protocols by the card networks) create a link between what the user wants, and what the agent searches for and buys.

- The intent is a cryptographically signed object that proves the user authorized the agent to look for these specific items.
- **Cart Mandate (The "Price Lock"):** When the merchant receives the intent, they return a Cart Mandate. They have to honor all fees and prices there.

#### New: Delegation

**Delegation is similarly L1.** The protocols are shipping, but the volume handshakes are very low.

The agent ↔ merchant handshake should define the secure two-way communications between checkout and end user. Today, multiple protocols overlap and compete:

- **TAP agent identity** (Visa/Mastercard's agent tokenization — linking an agent to a credential, and the credential back to a legal owner)
- **AP2 consumer authorization** (Google’s cryptographic mandates proving a user authorized a specific transaction - rail agnostic)
- **ACP session binding** (Stripe/OpenAI's commerce protocol, now folding into UCP compatibility)
- **UCP capability discovery** (the merchant publishes what they support; the agent negotiates from there)

One or more of these may apply to a given transaction depending on which rail it uses, with what merchant and PSP. None of them talk to each other seamlessly yet.

#### Policy: Emerging

**Policy is at L1**. Most merchants are actively considering how to block, manage, or build policies for bots or agents. This is something they’re trying to do unilaterally; it’s not something AI is helping to enshrine (yet).

What a merchant wants to sell and to whom was traditionally something they figured out after you walked into a store or landed on their website. They’d use data about you to figure that. Now, the merchant's risk assessment moves upstream. It's no longer just "is this card stolen?" — it's "do I want to sell to this specific agent behavior?"

Consider:

- A luxury brand might throttle agent purchases to preserve human-only drops.
- A commodity supplier might offer agent-only pricing for off-peak fulfillment windows.
- A merchant with thin margins might reject any agent transaction where they can't verify the identity chain back to a legal owner.

Merchants already have risk engines, but now they need to add a new fundamental question: is this an agent, and do I want to sell to it?

#### Cart: Emerging

**The cart is at L1**, with L2 very early, but could change rapidly. UCP just shipped cart capability in April. Walmart's early data suggests agent-rendered carts convert worse than websites.

Whether you get the sale as a merchant is all about tiny micro optimizations across the website and in the cart, from page load to upsell, to shipping choices presented; everything matters. When you own it you’re in control. But the agentic shopping cart is different.

It used to be something the merchant trapped the customer into converting. Now the agents can render the cart and bring it to the merchant. The agent now brings a signed intent to the merchant in the session, instead of the merchant trapping a user in its flow.

UCP's [April 2026 update](https://blog.google/products-and-platforms/products/shopping/ucp-updates/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) added a Cart capability — agents can now save or add multiple items to a shopping cart at once from a single store. It also added a Catalog capability (agents retrieve real-time product details — variants, inventory, pricing) and Identity Linking (loyalty/member benefits carry across platforms).

That shifts some of the power dynamic and is a work in progress. Walmart's data says the jury is *not* out: [purchases inside ChatGPT converted at one-third the rate of click-throughs to](http://walmart.com/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) [Walmart.com](https://walmart.com/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com); delivering a 1.18% conversion rate with 77% cart abandonment vs. the industry average of 2.5–3%. That will most likely change in time, but right now the merchant's own checkout still wins.

#### Payment (Authorization)

**Payment is at L1**. 95% of AI-driven commerce still completes on the merchant's own site. The human clicks buy.

The moment a person clicks "pay" and the customer commits to buy the items has evolved, but has been functionally similar for decades. Now the card networks, payment service providers (PSPs), and merchants are launching new protocols to attempt to secure what this looks like with agents (See: [Agentic Payments Map](https://www.fintechbrainfood.com/p/the-agentic-payments-map)).

In e-commerce specifically, there's overlap between what's happening with the AI labs, PSPs, and card networks:

- **Visa and Mastercard have new protocols for agents to pay (auth).** They carry the agent's intent, and match what the user's intent was with the merchant directly in their network.
- **They're also working on agent identity.** Linking an agent to a credential, like a card, also links it back to a legal owner, like a company or consumer.

But payments are still the *least* impacted stage of the lifecycle. The eMarketer analysis of Stripe's annual letter notes that in 2026, [95% of e-commerce sales driven by AI platforms will still be completed off the AI platform and on the merchant site](https://www.emarketer.com/content/stripe-appraises-agentic-commerce-landscape-2025-annual-letter?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com). The agent drives discovery. The human still clicks "buy."

#### Fulfillment and Loyalty

**Fulfillment is also L1**. It relies on the cart building being the norm and agents increasingly being able to observe and manage shipping.

Most people don't think about shipping until it breaks.

E-commerce companies worked incredibly hard to make shipping feel seamless and near instant. But there are edge cases fraudsters using valid (but stolen) payment credentials with different addresses. Now throw agents into the mix, and you have a whole swathe of new potential risks.

UCP's spec already includes fulfillment events — tracking numbers, delivery confirmations, and refund adjustments are part of the protocol's order lifecycle. The [April 2026 UCP update](https://blog.google/products-and-platforms/products/shopping/ucp-updates/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) also introduced Identity Linking, so shoppers on UCP-integrated platforms receive the same loyalty or member benefits they'd get when logged into a retailer's own site. That's the beginning of a post-purchase trust chain for agents: the same identity that authorized the purchase can verify delivery.

So it’s pretty clear, *we’re still early*, but the good news is, each step will become more autonomous, and everything in AI has a habit of being tiny until it’s absolutely not. You don’t want to be the wrong side of that kind of shift.

Borrowing unapologetically from the self-driving lore, [Stripe coined the 5 levels of agentic commerce in their annual letter](https://stripe.com/annual-updates/2025?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) this year:

- Level 1: Humans choose items, agents complete the purchase
- Level 2: Agent researches items, presents them to the human, the human chooses, and the agent buys
- Level 3: Human delegates an action (e.g. buy coffee beans for under $20) and the agent completes the task and purchases
- Level 4: Agent manages complex buying tasks — replenishing inventory or managing subscriptions, enforced with policies
- Level 5: The agent anticipates needs and buys things

I think these are somewhat imperfect because they don't map across the whole journey, and they don't represent what's happening today as much. In reality, humans are primarily using agents to help research items and present them to humans, but the agent almost never buys, so Stripe's Level 1 and 2 aren't quite right either. If we take self-driving and then map it to commerce, it might look something more like this:

| **Level** | **Driving Example** | **Commerce Example** |
| --- | --- | --- |
| **1: Assistance** | Cruise control / Lane keeping | Agent suggests products and merchants based on your query |
| **2: Partial Automation** | Can control speed and steering on highways | Agent finds products, builds a cart, and presents options for you to approve |
| **3: Conditional Automation** | Can manage specific conditions (like traffic jams) | Agent builds the cart and completes purchase for merchants where you have stored credentials and pre-approved policies |
| **4: High Automation** | Geofenced areas fully automated (e.g., Waymo) | End-to-end autonomy for specific merchants or categories (e.g., your agent manages all Amazon Subscribe & Save, choosing suppliers on price and reviews) |
| **5: Full Automation** | Can drive anywhere, any time without assistance | Agents can buy anything from anywhere, any time. Your household inventory, subscriptions, and procurement run on autopilot. |

After 2,000 words, we can now finally justify why each step is at a given level of autonomy and begin to think about how they become more autonomous.

Today, discovery might be at Level 3 already (agents parse thousands of SKUs without asking). Payment is stuck at Level 1 (the human still clicks "buy"). Fulfillment is barely at Level 1 (although Shop Pay and Amazon do some nice work at least remembering you and your preferences). But here’s the current heatmap from the open, now fully explained.

![](https://media.beehiiv.com/cdn-cgi/image/fit=scale-down,quality=80,format=auto,width=720,onerror=redirect/uploads/asset/file/b25dc6bd-075c-45ca-b4ac-72ee77136e55/image.jpeg)

The Fintech Brainfood Agentic Commerce Autonomy Matrix

**What would it take to move to the next stage in each layer?**

- **Discovery & Referral (L4 within 18 months):** The biggest gap is merchants and commerce platforms increasingly optimizing for AI agent search, adding their schemas and llms.txt. Merchants and their back-end commerce stack need to ensure they’re available for look-up via the UCP protocol. As more merchants do this, discovery and referral will become “high” within 18 months. There will still be laggards and there’s work to do on the agent experience (chat still doesn’t feel like it).
- **Intent & Delegation (L3 within 18 months):** We have the protocols for sharing intent, but they’re not widely adopted; there’s an entire question of liability and risk here that card networks are strong at. But until merchants feel like there’s either enough volume, and/or a clear liability framework, this will be stuck. I expect the card networks to lead on this by the end of the year and we’ll see some types of transactions begin to be *better* via agentic than via e-commerce.
- **Policy & Cart (L2 within 12 months):** The easiest thing for merchants to do is define what they’re willing and not willing to sell via agents. The best way to do this is to define policies on a binary yes / no basis for LLMs. More nuanced fraud signals will be harder to pull through protocols and will take some heavy engineering work and partnership from the labs and agents to figure out.
- **Payment & Fulfillment (L2 within 12 months):** Again, the key here will be scheme rulebooks defining what the agents at labs can do on their network and what disputes and chargebacks look like (and what compelling evidence needs to be). The unlock for policies (above), would be some sort of shared way for merchants to gather signals from known LLMs (like OpenAI) for presentation as evidence to dispute a chargeback.

The assumption on all of the above here is that this is an agent from a known big company. That means over time those agents need to become wallets, and more securely store credentials (in something like Stripe Link, Apple Pay or Shop Pay). Those integrations are early and janky, but will improve.

My prediction is, however, we’ll see an explosion of Openclaw-like, 3rd party agents from Fintech companies, Neobanks, payments providers, and new market entrants. That complicates the adoption picture.

Still, if we assume this is coming, the next thing we do is make it all flow end-to-end.

### 3\. This Process Isn't Yet End-to-End or Connected

Each stage of the commerce process has evolved over the past two decades with each participant optimizing their part of the stack to maximize conversion. We’re entering a world with new steps to the process, new user journeys, and new ecosystem participants. We’re still experimenting with how all of this fits together coherently.

The protocols we’ll use aren’t fully settled, and each stage has different technical requirements. Payments are deterministic, consumers and AI are probabilistic. So the agent is selecting something *it thinks you want*, and you could issue a chargeback because *you didn’t really want that thing your agent thought you want*. Who’s liable? How can that be transmitted between agent, merchant and network?

Today each protocol and technology covers a slice of the journey:

- Discovery runs on llms.txt and [Schema.org](https://schema.org/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com).
- UCP handles the merchant manifest and checkout session.
- AP2 handles payment authorization with cryptographic mandates.
- Visa and Mastercard are building their own agent tokenization.

And they were all built by different parties with different incentives.

That’s why 95% of AI-platform-driven e-commerce still completes on the merchant's own site (eMarketer). Shopify's data shows the top of the funnel is working spectacularly (13x order growth from AI search). But almost nobody is checking out *inside* the AI. The discovery-to-payment gap is massive.

I'm already tired of making the joke that there are more agentic commerce protocols than payments. But of course, that's logical if you consider that the diffusion of innovation takes time. And it's far easier to have LLMs help you in marketing than it is to give them a wallet and let them yolo purchase everything for you or your company.

So if it’s so messy, why is everyone piling in?

#### There’s value in betting ahead.

The reason every payments company, AI lab, and tech company is thirsty to be seen in agentic commerce is that the pattern works.

Stripe had some interesting data from their annual letter. Take Atlas, the product that lets you incorporate a company in a few hours. When they launched in February 2016, it wasn’t because there was a mature market for streamlined company formation. Since the arrival of AI, company formations have been up 41% YoY. The thesis being, AI lets people build more with less. And that, ladies and gentlemen, is called a *leading indicator*.

PayPal, Checkout, Adyen, Stripe, Visa, Mastercard and the major merchants have now all backed the Universal Commerce Protocol (UCP), as I explored in [AI the checkout is becoming a reality](https://www.fintechbrainfood.com/p/ai-checkout):

❝

The danger here is complacency. When the early-adopter crowd is rushing into something and getting value from it, that's your signal to pay attention. These are businesses reacting to actual customer demand. What the early adopters are doing today will be universal in 10 years. And it has never been cheaper to experiment or build.

[AI, the checkout is becoming a reality](https://www.fintechbrainfood.com/p/ai-checkout)

When the volume arrives, the infrastructure providers with live integrations win.

### 4\. The Commerce Journey Will Get Connected

When the prize is this big, you can bet the world's biggest companies will do what it takes to jump on that money train.

Which will create new problems. Like auditability.

When five protocols handle five stages, nobody has the complete transaction trail. Visa sees the payment authorization, Shopify sees the cart. Google's UCP sees the checkout session and AP2 / the AI lab sees the user's intent. The merchant sees the fulfillment.

But nobody sees all of it end-to-end.

The compliance infrastructure isn't ready for a world where the intent, the identity, and the payment all live in different systems. When you fragment the audit trail across five protocols managed by five different governance bodies, you create a vacuum. Which is why [Target updated its terms to treat AI agent purchases as "transactions authorized by you"](https://www.emarketer.com/content/target-limits-liability-ai-shopping-assistants-gain-traction?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) meaning customers pay for agent mistakes and [Amazon sued Perplexity and got a federal injunction blocking its Comet browser agent](https://www.pymnts.com/amazon/2025/amazon-tightens-platform-access-as-ai-shopping-agents-expand/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) from making purchases on its platform.

We don’t yet have persistent agent identity; we have slices of it. Visa’s TAP protocol links an agent to a card, which is linked to its legal owner, and UCP’s identity linking lets agents carry loyalty across platforms. But these are parallel. There’s no handshake between just these two (yet), and now multiply this by all networks, merchants, and AI agents.

This problem too will be solved in time. I found it *very* interesting that the [FIDO Alliance launched an Agentic Authentication Working Group](https://fidoalliance.org/fido-alliance-to-develop-standards-for-trusted-ai-agent-interactions/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) in April, drawing initial contributions from Google (AP2) and Mastercard (Verifiable Intent). OpenAI joined FIDO's board the same month. The people who invented passkeys are now working on agent identity, and the fact that AP2 and Verifiable Intent are being contributed to a shared standards body means the protocols are starting to converge.

And if giant standards efforts sound slow, and like they’ll take time to deliver, then yes you’re right most of the time. But the *sheer pace* of AI change is the x factor here. You cannot control for Anthropic waking up one day and solving everything.

### 5\. And When It Does, Everything Changes

Agents are a new economic actor. They’ll buy things for themselves, they’ll choose *what* to buy and become customers in their own right.

That makes this shift *far bigger* than mobile or e-commerce in the long run.

As economic actors, agents can choose merchants based on infinitely more research, cost comparison, and they're less susceptible to advertising. An agent doesn't care about your Instagram ad. It cares about structured data, pricing accuracy, inventory availability, and return policies. The merchant's job shifts from "convince the human" to "be machine-readable and competitively priced."

As a merchant, your ability to make sales and continue to grow depends on being able to interact with them as seamlessly as possible.

Yes, humans will always enjoy shopping, in person, online, and I'm pretty sure there will still be plenty of ads. But if you're thinking about agentic commerce as a channel, you're missing the monumental shift they could represent.

What's harder to judge is the timing and segments. Agents could be meaningfully more impactful on commodity goods, fast fashion, and consumer electronics — anything where the buying decision is mostly about price, availability, and specs. These are the categories where an agent can genuinely replace human judgment. High-consideration purchases (luxury, bespoke, experiential) stay human longer.

But if you put these ideas together

1. AI has a habit of changing from 0 to 100 overnight and
2. Agents are becoming economic actors making purchase decisions

Then you can’t ignore this shift.

Agents might be the biggest change to our economic actors since limited liability companies. Corporations gave is procurement departments, B2B commerce and much larger transactions.

What will agents bring us?

And do you want to build for that now or catch up later?

ST.

### 4 Fintech Companies 💸

**1.** [Compute Desk](https://www.compute-desk.com/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) **\- Pricing and hedging for GPU compute markets**

Compute Desk builds price discovery and financial instruments for the GPU compute market. Letting providers, lenders and buyers price, hedge and transact compute capacity the way commodity markets do. Their pricing index is one of three on Bloomberg terminals and aggregates at the NVIDIA Hopper architecture level. As of early 2026 they're showing zero on-demand availability across 90% of providers, and have seen renters subletting clusters.

🧠 **Compute as a commodity, so we need price discovery, hedging instruments, eventually derivatives. With BlackRock’s CEO calling for exactly that recently.** Bloomberg inclusion is a signal that institutional buyers and sellers want this market structure to exist. However, commodity markets need a fungible underlying asset, and an H100 is not a B200 is not a GB200. Corn is still corn.

**2.** [Prime Intellect](https://www.primeintellect.ai/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) **\- Aggregated Compute and Training Infrastructure.**

Prime Intellect aggregates GPU demand to help companies build evals and fine-tune models or agentic loops to their use case. They’ve supported companies like Ramp, Browserbase, and even Nvidia in training or fine-tuning models. They have pre-made and hosted “evals” to help you know if your model is performing; they host the training, deployment, and improvement feedback loops of new models created.

🧠 **This is how you build your own foundation model without building a hyperscaler data center.** If GPU markets become more commoditized, GPU compute aggregation becomes a key skill. The only missing part is an actual competitive cost marketplace for that GPU/dollar. *(Aside: Unlike every “decentralized compute” project in crypto, Prime Intellect has customers. Bittensor gets a lot of hype, but most of its clients are crypto projects. )*

**3.** [Internet Backyard](https://www.internetbackyard.com/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) **\- Stripe Billing for GPU compute providers**

Internet Backyard automates billing, usage metering and order-to-cash workflows for data centers and GPU providers like quoting, metering, invoicing, collections and payment routing. Their first product gnomos handles the spreadsheet-and-manual-handoff work that sits between sales, ops and finance at most compute providers today. The longer-term thesis is becoming the data layer that aggregates GPU benchmarks and pricing across the industry.

🧠 **The "Stripe for GPU billing" angle is sharp, but the question is whether horizontal usage-base billing platforms (Stripe Metronome, Orb) absorb this from above**. The genuine wedge is that the compute economy is fragmented in a way SaaS isn't — neoclouds, regional colos and small GPU providers don't have the engineering teams to glue a generic billing API into their stack. Taking a percentage of recovered invoices plus payment routing fees is a smart pricing model. They’re hinting at using billing to aggregate data, but that depends on them getting enough market share first.  
  
**4.** [Nevis Wealth](https://www.neviswealth.com/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com) **\- The AI for Wealth Management**

Nevin aims to reduce the admin burden on wealth advisors by auto-creating briefings pre-meeting, capturing notes during meetings, turning those into tasks, and helping with time-consuming tasks like account opening. Critically, they’re selling on never training on data and ensuring nothing is sent to the labs.

🧠 **Is this the “Harvey of wealth management?”** Harvey is considered the breakout vertical AI success in legal, arguably Hebbia in capital markets. Nevis seems to have some traction, but this is a crowded space. The "AI for advisors" category has filled out fast — Jump, Zocks, Powder, Holistiplan, plus AI agents being bolted directly into Orion, Wealthbox, and Salesforce Financial Services Cloud. What's the wedge that makes Nevis the system of record, not a side panel that gets absorbed?

### Things to know 👀

**1.** [Google announces Universal Cart.](https://blog.google/products-and-platforms/products/shopping/google-shopping-cart/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com)

At Google I/O this year, Google announced its Universal Shopping Cart. When you’re searching for products, the cart works across merchants, letting users add items as they browse, watch YouTube, or do email. When an item is added, the cart starts to look for better prices at other merchants, or it will notify you when an item is back in stock. It also does some smart things, like identifying if you buy RAM that is incompatible with a motherboard in the cart. It rolls out this summer in the US in search and Gemini.

🧠 **Is it me or is this absolutely massive?** Google Shopping always showed SKUs when you searched, but now the cart just follows you. Imagine when they embed this into Chrome. The aggregator becomes even more powerful, but merchants potentially lose some brand affinity.

🧠 **UCP is a Trojan horse.** The Universal Commerce Protocol makes merchants and their SKUs headless. That’s a good thing for letting agents securely buy them, and managing consumer “intent” (did they really want to buy the thing). Now UCP is live with an increasing number of PSPs and merchants, the cart can be anywhere. So yes, Gemini, but why not search too?

2\. [White House Issues Executive Order for Fintech Innovation](https://www.whitehouse.gov/fact-sheets/2026/05/fact-sheet-president-donald-j-trump-integrates-financial-technology-innovation-into-regulatory-frameworks/?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com)

The White House issued an executive order requiring the federal financial services regulators, like the SEC, CFTC, FDIC, OCC, CFPB, and NCUA, to identify rules that block fintechs within 90 days. The agencies then have 180 days to act. Separately, the Fed gets 120 days to report on whether non-bank fintechs, including digital asset firms, can get direct access to Federal Reserve payment accounts.

🧠 **The goal is to identify rules that could be updated to facilitate innovation and competition.** I don’t believe there was a clear mandate for competition in regulation before this moment. And there was a general sense that regulators viewed larger incumbents as safer, and therefore preferable.

🧠 **Regulators should encourage innovation by institutions of all sides.** The lived experience of many banks was that this was categorically not the case historically. Nobody gets fired for buying from a supplier that is familiar to regulators under the Bank Service Company Act (BCSA). This became a negative spiral for companies not yet on that list, and banks trying to pass exams where regulators hadn’t seen that vendor before.

🧠 **The other big push is for master account access.** For years, fintechs and crypto firms have been trying to get master accounts at the Fed. Individual Reserve Banks could grant or deny applications on their own, without Fintech companies claiming a lack of transparency. This EO asks the Fed to report on whether that kind of independent action by Reserve Banks is even legally permissible. And if so, what policies should exist to make the process consistent across all twelve banks.

🧠 **Rules can be made, unmade, and administrations can change**. I’m broadly pro-innovation and pro-fintech, especially when it raises the bar and enables incumbents and innovators to better serve customers with technology. But we have to have the stomach to keep that goal, even when there’s a disaster, as we saw with Synapse, SVB, Silvergate, and others.

3\. [Mercury raises $200m Series D at $5.2bn valuation](https://www.linkedin.com/posts/iakhund_today-mercury-announced-a-200m-series-d-share-7462880144802803714-01uz?utm_source=share&utm_medium=member_desktop&rcm=ACoAAAGug9MBUqEhGsxDPiMdpLsqhjhZM3W18Yk)

Mercury raised $200 million at a $5.2 billion valuation, a 49% jump over its last round, led by TCV and including Sequoia, Andreessen Horowitz, and Coatue. The raise came weeks after conditional approval from the OCC to become a federally regulated bank and had entered their mobilization phase.

🧠 **The neobank class of 2019 has completely reshuffled.**

- Brex got acquired by Capital One for $5.15B.
- Ramp became an AI spend management company valued north of $20B.
- Mercury chose to become an actual bank.

Three companies that started in the same space now occupy completely different strategic positions.

🧠 **Mercury filed with the OCC in December 2025 and got conditional approval by April 2026. Final approval expected 2027.** Once chartered, they hold deposits directly, join Zelle, expand lending, and stop sharing revenue with partner banks Column and Choice Financial. The margin they give away today? They keep it. A $650M revenue fintech and a $650M revenue bank are wildly different businesses.

🧠 **AI is a tailwind for Mercury.** Mercury said they saw 2.5x more applications Q1 2026 vs Q1 2025. AI is creating a new generation of founders who need a bank account from day one. Just as new apps in the app store are spiking, Stripe Atlas signups are spiking. If you’re serving young growth companies, you win when they are born.

### Good Reads 📚

**1.** [Simulated learning for Regulatory Examiners](https://mhsu2112.substack.com/p/the-dojo?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com)

Regulatory examiners have a hard time early in their careers when examining a bank if they lack experience. Experienced banks can push back; risk can be hiding in countless corners that no classroom can prepare you for. So Mike Hsu, former Acting Comptroller of the Currency no less, vibe-coded a “Dojo” (themed on the Matrix training environment) to put examiners through mock exams with banks.

🧠 A few thoughts. 1) Every agency should adopt this immediately. 2) So should companies that want to train up young staff. 3) Mike is a unique animal. How many former senior regulators have a Substack and public Vibe-coded projects out there?

**2.** [Policy as code](https://mhsu2112.substack.com/p/policy-as-code?utm_campaign=how-commerce-is-being-reinvented-for-agentic-ai&utm_medium=referral&utm_source=www.fintechbrainfood.com)

And if a regulator vibe coding an exam simulator bakes your noodle, imagine if we could turn policy into code. Let’s be honest, there’s a LOT of policy, most of it PDFs. Machines *can* read PDFs, but they prefer markdown. Mike turns one reg from a PDF, into text, into markdown with a YAML formatter (and built a demo translating it). Then, it asks the most interesting question: what if regulators turned policy into markdown while drafting it? Mike made a prototype to do that, too, which automatically flags overlap with any old policies.

🧠 Can every regulator adopt this ASAP, please? Can every compliance team use the YAML converter and open source it / get it behind it too? Thx.

### That's all, folks. 👋

*(1) All content and views expressed here are the authors' personal opinions and do not reflect the views of any of their employers or employees.*

*(2) All companies or assets mentioned by the author in which the author has a personal and/or financial interest are denoted with a* \*. *None of the above constitutes investment advice, and you should seek independent advice before making any investment decisions.*

*(3) Any companies mentioned are top of mind and used for illustrative purposes only.*

*(4) A team of researchers has not rigorously fact-checked this. Please don't take it as gospel—strong opinions weakly held*

*(5) Citations may be missing, and I’ve done my best to cite, but I will always aim to update and correct the live version where possible. If I cited you and got the referencing wrong, please reach out*