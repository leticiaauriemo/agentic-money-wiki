---
title: "Three Gaps That Will Decide Which Banks Are Ready For Agentic Payments"
source: "https://www.forbes.com/councils/forbestechcouncil/2026/04/21/three-gaps-that-will-decide-which-banks-are-ready-for-agentic-payments/"
author:
  - "[[Dimitar Dimitrov]]"
published: 2026-04-21
created: 2026-04-21
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

The constraint, in my experience, is architectural. Every layer of existing infrastructure was built around one assumption: A human is behind every transaction. Agentic AI surfaces three specific places where that assumption breaks, and where the decisions made in the next months will determine which banks are positioned to handle what's coming.

AI fraud detection in banking rests on the core idea that there's a person on the other side of every transaction, spending money in predictable ways. Those models are good at what they were designed for. The challenge is that a legitimate AI agent and a malicious one can look identical to them.

That blind spot puts a choice on your table that most banks haven't yet brought to the leadership level: Tighten controls and block legitimate agent payment volume or loosen them and your fraud exposure grows.

Most executives I've spoken with respond by adjusting thresholds and refining detection rules, convinced that better calibration will close the gap. But the underlying model wasn't built to distinguish between transaction patterns that have no human origin at all, and recalibrating it doesn't change that.

Ask your fraud team to run a test: known agent-initiated transactions alongside known automated fraud, through your existing detection system. If the system can't reliably tell the difference, that's your answer. The next step is commissioning a separate model built specifically for nonhuman transaction behavior, running alongside what you already have.

<video aria-label="Connatix video player" role="application" title="" src="blob:https://www.forbes.com/4c883f46-e023-40e9-a82d-38c7e60eb15f" controls=""></video>1/1

00:24

Forbes Innovation

In our work with a U.K. bank, the decision that made the difference was treating this as an identity problem from the start. Instead of adjusting what the existing system was looking for, we built a separate detection capability trained on transaction patterns with no human actor behind them. The result was a meaningful reduction in fraudulent applications that the primary system had no way of catching.

Every bank I've worked with has had the same conversation about authentication: What does the customer do to confirm the payment? They tap, scan and enter a code. [PSD3](https://www.ey.com/en_be/technical/financial-services/financial-services-alerts/psd3-impacts-on-payment-and-electronic-money-institutions-get-ready) (the EU's revised payment services directive) addresses this by requiring authentication only once, when the payment arrangement is first set up, not for every subsequent transaction. But banks can't wait for legislative clarity while their customers' agents are already initiating transactions.

What works is moving authentication upstream entirely, from the moment of payment to the moment an agent is set up. The trust decision is made once, at onboarding, and it carries forward. The per-transaction check becomes largely redundant because the hard judgment was already made before any payment was initiated.

However, the authentication question gets solved at the ownership level, long before it reaches the technical teams. Security, product and legal each have a stake in the answer, and every time I've seen a bank move quickly on this, there was one person at the executive level who stepped in early and decided who leads. As a CTO or CIO, that person is you.

Name a single owner for the authentication decision. Give them 30 days to map every point in your payment flow where authentication currently requires a human and return with a proposal for how each one works in an agent-initiated transaction. Those two steps tend to drive more progress than months of cross-functional discussion.

Banking APIs are designed for human-paced interactions, not the velocity and volume that agentic payments demand. When AI agents execute sequences of interdependent transactions, that design becomes a constraint on which payment ecosystems a bank can participate in. [Accenture](https://bankingblog.accenture.com/agentic-payments-commerce) surveyed over 200 CTOs and heads of payments and found that 85% said their current systems can't handle autonomous agent-initiated transactions at scale.

Core replacement is the wrong bet. It takes years, the risk compounds at every stage and you don't need to go that far. A capable front end that handles agent requests while your existing systems run as normal gets you there faster. [Goldman Sachs](https://www.goldmansachs.com/what-we-do/transaction-banking/why-ai-and-apis-are-strategic-imperatives) pointed to the same priority publicly, describing the work of making their APIs AI-agent friendly as a key strategic focus.

The first thing I'd request is a clear picture of exposure: Which of your top payment volume flows run through ecosystems that are already moving to agent-initiated transactions, and which of those can your current infrastructure handle? Once your technology team gives you both answers, the decision about whether to build that capability internally, work with a partner or combine the two becomes straightforward.

Deloitte estimates agentic commerce could account for up to [$17.5 trillion](https://www.deloitte.com/us/en/Industries/financial-services/articles/how-agentic-ai-is-transforming-e-commerce-and-commerce-payments.html) in global commerce by 2030. That means the infrastructure decisions you make in the next 12 to 18 months will determine which institutions are positioned to capture that volume and which aren't.

The three gaps above are solvable. Getting there takes deliberate decisions, a willingness to rebuild and the recognition that the systems in place were designed around constraints that no longer apply. The ones who decide to move early will simply be in a stronger position, with infrastructure that holds up over time.

---

[Forbes Technology Council](https://councils.forbes.com/forbestechcouncil?utm_source=forbes.com&utm_medium=referral&utm_campaign=forbes-links&utm_content=in-article-ad-links) is an invitation-only community for world-class CIOs, CTOs and technology executives. [*Do I qualify?*](https://councils.forbes.com/qualify?utm_source=forbes.com&utm_medium=referral&utm_campaign=forbes-links&utm_term=ftc&utm_content=in-article-ad-links)

---

FORBES’ VIDEO WILL PLAY AFTER THIS AD The video player is currently playing an ad.FORBES’ FEATURED Video