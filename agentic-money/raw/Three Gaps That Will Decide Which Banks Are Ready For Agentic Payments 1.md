---
title: "Three Gaps That Will Decide Which Banks Are Ready For Agentic Payments"
source: "https://www.forbes.com/councils/forbestechcouncil/2026/04/21/three-gaps-that-will-decide-which-banks-are-ready-for-agentic-payments/"
author:
  - "[[Dimitar Dimitrov]]"
published: 2026-04-21
created: 2026-04-25
description: "The ones who decide to move early will simply be in a stronger position, with infrastructure that holds up over time."
tags:
  - "clippings"
---
![Forbes Technology Council](https://blogs-images.forbes.com/assets/images/avatars/blog-3949_400_6d18078e84d93600baaf18165a1394f8.jpg)

By [Dimitar Dimitrov](https://www.forbes.com/councils/forbestechcouncil/people/dimitardimitrov/ "https://www.forbes.com/councils/forbestechcouncil/people/dimitardimitrov/"),

Forbes Councils Member.

for [Forbes Technology Council](https://www.forbes.com/councils/forbestechcouncil/)

COUNCIL POST

Expertise from Forbes Councils members, operated under license. Opinions expressed are those of the author.

| Membership (fee-based)

*Dimitar Dimitrov is the founder and Managing Partner at* [*Accedia*](https://accedia.com/)*, a leading European AI & Custom Software Development Company.*

![ ](https://imageio.forbes.com/specials-images/imageserve/67ffcb9ff12b40508f89808e//0x0.jpg?width=960&dpr=1)

getty

Agentic payments arrived faster than most of us anticipated. Visa, Mastercard, Stripe, Google and PayPal all shipped agentic commerce frameworks within a six-month window in 2025. Hundreds of live agent-initiated transactions have already cleared, yet the industry's conversation has stayed on what this means for consumer experience and network innovation.

What's received far less attention is what agentic payments mean for banks. Are they ready to be on the other end of those transactions where they're expected to approve payments that no human ever initiated? In most cases, the honest answer is no.

PROMOTED

## Where The Human Assumption Breaks

The constraint, in my experience, is architectural. Every layer of existing infrastructure was built around one assumption: A human is behind every transaction. Agentic AI surfaces three specific places where that assumption breaks, and where the decisions made in the next months will determine which banks are positioned to handle what's coming.

### 1\. Fraud Models That Can't Tell A Legitimate Agent From A Malicious One

AI fraud detection in banking rests on the core idea that there's a person on the other side of every transaction, spending money in predictable ways. Those models are good at what they were designed for. The challenge is that a legitimate AI agent and a malicious one can look identical to them.

That blind spot puts a choice on your table that most banks haven't yet brought to the leadership level: Tighten controls and block legitimate agent payment volume or loosen them and your fraud exposure grows.

Most executives I've spoken with respond by adjusting thresholds and refining detection rules, convinced that better calibration will close the gap. But the underlying model wasn't built to distinguish between transaction patterns that have no human origin at all, and recalibrating it doesn't change that.

Ask your fraud team to run a test: known agent-initiated transactions alongside known automated fraud, through your existing detection system. If the system can't reliably tell the difference, that's your answer. The next step is commissioning a separate model built specifically for nonhuman transaction behavior, running alongside what you already have.

In our work with a U.K. bank, the decision that made the difference was treating this as an identity problem from the start. Instead of adjusting what the existing system was looking for, we built a separate detection capability trained on transaction patterns with no human actor behind them. The result was a meaningful reduction in fraudulent applications that the primary system had no way of catching.

### 2\. Authentication Frameworks Built For A Different Transaction Model

Every bank I've worked with has had the same conversation about authentication: What does the customer do to confirm the payment? They tap, scan and enter a code. [PSD3](https://www.ey.com/en_be/technical/financial-services/financial-services-alerts/psd3-impacts-on-payment-and-electronic-money-institutions-get-ready) (the EU's revised payment services directive) addresses this by requiring authentication only once, when the payment arrangement is first set up, not for every subsequent transaction. But banks can't wait for legislative clarity while their customers' agents are already initiating transactions.

What works is moving authentication upstream entirely, from the moment of payment to the moment an agent is set up. The trust decision is made once, at onboarding, and it carries forward. The per-transaction check becomes largely redundant because the hard judgment was already made before any payment was initiated.

However, the authentication question gets solved at the ownership level, long before it reaches the technical teams. Security, product and legal each have a stake in the answer, and every time I've seen a bank move quickly on this, there was one person at the executive level who stepped in early and decided who leads. As a CTO or CIO, that person is you.

Name a single owner for the authentication decision. Give them 30 days to map every point in your payment flow where authentication currently requires a human and return with a proposal for how each one works in an agent-initiated transaction. Those two steps tend to drive more progress than months of cross-functional discussion.

### 3\. Banking APIs That Can't Keep Pace With Agent-Driven Commerce

Banking APIs are designed for human-paced interactions, not the velocity and volume that agentic payments demand. When AI agents execute sequences of interdependent transactions, that design becomes a constraint on which payment ecosystems a bank can participate in. [Accenture](https://bankingblog.accenture.com/agentic-payments-commerce) surveyed over 200 CTOs and heads of payments and found that 85% said their current systems can't handle autonomous agent-initiated transactions at scale.

Core replacement is the wrong bet. It takes years, the risk compounds at every stage and you don't need to go that far. A capable front end that handles agent requests while your existing systems run as normal gets you there faster. [Goldman Sachs](https://www.goldmansachs.com/what-we-do/transaction-banking/why-ai-and-apis-are-strategic-imperatives) pointed to the same priority publicly, describing the work of making their APIs AI-agent friendly as a key strategic focus.

The first thing I'd request is a clear picture of exposure: Which of your top payment volume flows run through ecosystems that are already moving to agent-initiated transactions, and which of those can your current infrastructure handle? Once your technology team gives you both answers, the decision about whether to build that capability internally, work with a partner or combine the two becomes straightforward.

## Will Your Bank Be Ready For Agentic Payments?

Deloitte estimates agentic commerce could account for up to [$17.5 trillion](https://www.deloitte.com/us/en/Industries/financial-services/articles/how-agentic-ai-is-transforming-e-commerce-and-commerce-payments.html) in global commerce by 2030. That means the infrastructure decisions you make in the next 12 to 18 months will determine which institutions are positioned to capture that volume and which aren't.

The three gaps above are solvable. Getting there takes deliberate decisions, a willingness to rebuild and the recognition that the systems in place were designed around constraints that no longer apply. The ones who decide to move early will simply be in a stronger position, with infrastructure that holds up over time.

---

[Forbes Technology Council](https://councils.forbes.com/forbestechcouncil?utm_source=forbes.com&utm_medium=referral&utm_campaign=forbes-links&utm_content=in-article-ad-links) is an invitation-only community for world-class CIOs, CTOs and technology executives. [*Do I qualify?*](https://councils.forbes.com/qualify?utm_source=forbes.com&utm_medium=referral&utm_campaign=forbes-links&utm_term=ftc&utm_content=in-article-ad-links)

---

NOW PLAYING: Miley Cyrus Explains Why Growing With Her Audience Means So Much To Her<video aria-label="Connatix video player" role="application" title="" src="blob:https://www.forbes.com/3cd5990e-d715-4ebe-8e68-33c7c63a2c9a" controls=""></video>

/

1/1

00:00

Miley Cyrus Explains Why Growing With Her Audience Means So Much To Her

Continue watching Miley Cyrus Explains Why Growing With Her Audience Means So Much To Her after the ad FORBES’ FEATURED Video

[Leadership](https://www.forbes.com/leadership/)

## AI Isn’t Limited By Innovation—It’s Limited By Infrastructure

![Dell Technologies](https://specials-images.forbesimg.com/imageserve/6256db2244135a1336404a9c/400x0.jpg?cropX1=47&cropX2=767&cropY1=9&cropY2=729)

By [Alison Biers](https://www.forbes.com/sites/delltechnologies/people/alisonbiers/ "https://www.forbes.com/sites/delltechnologies/people/alisonbiers/"),

Brand Contributor.

for [Dell Technologies](https://www.forbes.com/sites/delltechnologies/)

BRANDVOICE

Storytelling and expertise from marketers

| Paid Program

Apr 21, 2026, 08:53am EDT

![Leverage predictive analytics and overall equipment effectiveness (OEE) technology to identify potential issues before they occur in your manufacturing process.](https://imageio.forbes.com/specials-images/imageserve/69e64a8c78174795bd1bde05/Leverage-predictive-analytics-and-overall-equipment-effectiveness--OEE--technology-to/0x0.jpg?width=960&dpr=1)

Leverage predictive analytics and overall equipment effectiveness (OEE) technology to identify potential issues before they occur in your manufacturing process.

For the past two years, the conversation around artificial intelligence has been dominated by models—how powerful they are, how fast they’re improving and how broadly they can be applied.

But inside enterprises, a different reality is emerging.

AI isn’t stalling because of a lack of innovation. It’s stalling because of execution. More specifically, it’s constrained by infrastructure.

The organizations pulling ahead are not necessarily the ones with the most advanced models. They are the ones that can **move data faster, process it efficiently and deploy AI consistently at scale**. Everyone else is discovering that experimentation is easy, operationalization is not.

### The Shift from Experimentation to Execution

AI adoption is accelerating, but the nature of that adoption is changing. What began as isolated pilots is now expanding into core business processes. In fact, 65% of organizations are already scaling AI across their operations¹.

This shift matters.

AI is no longer confined to innovation labs. It is being embedded into customer experiences, supply chains and decision-making systems. It is moving from “interesting” to “indispensable.”

But this is where many organizations hit friction.

Running AI at scale is fundamentally different from testing it. Models must operate reliably, repeatedly and often in real time. They must integrate with existing systems and work across increasingly distributed environments.

In other words, AI only delivers value when the underlying infrastructure can support it.

### Rethinking the Role of the Cloud

For more than a decade, the default assumption was simple: put everything in the cloud.

And for many workloads, that still makes sense. Cloud platforms offer unmatched flexibility and access to on-demand resources, making them ideal for experimentation and rapid scaling.

But AI, particularly at scale, is exposing the limits of a cloud-only strategy.

As workloads become more data-intensive and persistent, new constraints emerge:

- Unpredictable and rising costs
- Latency that impacts real-time decisions
- Increased pressure around data control and sovereignty

This is not theoretical. 76% of organizations currently running AI workloads in the public cloud expect to move some or most of those workloads on-premises².

This shift is not about abandoning the cloud. It’s about recognizing that not all workloads belong there.

What’s emerging instead is a more deliberate model, one that places workloads where they perform best.

### The Rise of the Hybrid Reality

Leading organizations are not choosing between cloud and on-premises. They are designing for both.

Cloud remains critical for elasticity and rapid access to innovation. On-premises infrastructure plays an equally critical role in delivering performance, cost control and proximity to data.

This hybrid approach reflects a broader realization: AI performance is increasingly tied to where data lives and how efficiently it moves. When data must travel long distances or cross multiple environments, latency increases, costs rise and complexity compounds. Bringing compute closer to data, whether in a private data center or edge environment, can fundamentally change the equation.

This is less about ideology and more about physics.

### Complexity: The Quiet Constraint

Even with the right strategy, execution remains difficult.

33% of organizations cite technical complexity as the biggest barrier to AI adoption³. That complexity shows up everywhere: integrating new tools with legacy systems, managing fragmented data pipelines and operating across hybrid environments.

There is also a growing skills gap. AI infrastructure is not just about deploying hardware or software—it’s about orchestrating systems that must work together seamlessly under heavy demand.

Organizations that make progress tend to take a different approach. Instead of layering on more tools, they focus on simplification and integration, reducing friction across the stack and aligning infrastructure with business priorities.

Because in practice, the barrier is rarely access to technology.  
It’s the ability to use it effectively.

### The Economics Are No Longer Theoretical

For all the excitement around AI, the ultimate test is business impact.

Here, the data is increasingly clear. **84% of organizations report improved efficiency from AI investments** ⁴, with automation delivering measurable productivity gains. In some cases, employee productivity increases by up to 30%⁵.

These are not marginal improvements. They represent a shift in how work gets done.

At the same time, AI is unlocking new revenue streams, enabling organizations to create new products, enter new markets and deliver more personalized experiences.

But these outcomes are not automatic.

AI does not inherently reduce costs or increase efficiency. It does so only when it is deployed in the right environment, at the right scale and with the right infrastructure behind it.

### Preparing for What Comes Next

The next phase of AI is already taking shape.

Systems are evolving from tools that support decisions to systems that act on them, executing workflows, adapting in real time and operating with increasing autonomy.

This shift will amplify existing infrastructure demands.

Organizations will need environments that are:

- Scalable enough to handle sustained, high-volume workloads
- Resilient enough to support continuous operation
- Secure enough to protect increasingly valuable data

The decisions being made today about where and how to run AI will directly determine how well organizations can adopt these next-generation capabilities.

### Execution Will Define the Leaders

AI will continue to advance. Models will improve. Tools will become more accessible. But those advancements alone will not determine who leads. The differentiator will be execution, specifically, the ability to operationalize AI efficiently, securely and at scale. That requires a shift in mindset. Infrastructure is no longer a background consideration or a cost center. It is a strategic lever.

The organizations that recognize this and design their environments accordingly will not just keep pace with AI innovation; they will define its impact.

For actional strategies to drive innovation with AI, click [here](https://www.delltechnologies.com/asset/en-us/products/servers/briefs-summaries/ai-unleashed-transforming-business-it-ebook.pdf). The opportunity is clear. The technology is ready. The remaining question is execution.

[![Alison Biers](https://specials-images.forbesimg.com/imageserve/695c194a360262c30631f8a0/400x0.jpg?cropX1=0&cropX2=439&cropY1=13&cropY2=452)](https://www.forbes.com/sites/delltechnologies/people/alisonbiers/)

By [Alison Biers](https://www.forbes.com/sites/delltechnologies/people/alisonbiers/ "https://www.forbes.com/sites/delltechnologies/people/alisonbiers/")

BRANDVOICE | Paid Program

Alison Biers is a sales and marketing professional with 20-plus years of IT industry experience. In her role as Global Marketing Senior Director at Dell Technologies, Alison leads a team of product marketing professionals to increase global awareness for Server, Networking and Vertical Industries and helps customers gain the benefits of a purpose-built infrastructure by simplifying the path to success.

You've reached your limit of articles you can save without a subscription. Subscribe now to save as many articles as you want.

Premium Journalism, deeply reported stories and breaking news

Members-only events

[Subscribe](https://account.forbes.com/membership?eventSource=saveArticle)

Subscriptions renew automatically. You may cancel your subscription at any time.

<iframe src="about:blank"></iframe><iframe src="about:blank"></iframe><iframe src="about:blank"></iframe><iframe src="about:blank"></iframe>