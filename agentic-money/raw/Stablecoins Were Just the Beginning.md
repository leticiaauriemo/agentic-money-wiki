---
title: "Stablecoins Were Just the Beginning"
source: "https://www.currencyofpower.co/p/stablecoins-were-just-the-beginning"
author:
  - "[[Marieke Flament]]"
published: 2026-03-28
created: 2026-04-21
description: "Sean Neville on stablecoins, the singleness of money, and building a financial institution for AI agents"
tags:
  - "clippings"
---
<video title="Stablecoins Were Just the Beginning" src="blob:https://www.currencyofpower.co/368b6ba3-a8a7-4c42-be03-e7170c2e2089" controls=""></video>

Preview

Sean Neville on stablecoins, the singleness of money, and building a financial institution for AI agents

![](https://substackcdn.com/image/fetch/$s_!yv9l!,w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb833d5f9-41f0-446d-9046-84c987aea86e_2914x2098.png)

**Sean Neville has spent** thirty years asking the same question in different forms: what happens when you put a system that was built by gatekeepers onto rails that have none?

Sean started as a coder and composer, building software in the early days of the web at a time when most people were still paying monthly fees to send each other emails within a single walled garden. He watched the internet dissolve those walls for content and data, then spent the next decade questioning why money had been left behind. It is the quest to answer that question that led him and Jeremy Allaire to found [Circle](https://www.circle.com/) in September 2013, with a simple and radical premise: that the dollar, like the documents and the emails before it, should move on open rails.

The path from that premise to a working product was not straight. Circle tried consumer payments, OTC trading, crypto investing, and several versions of what would eventually become [USDC](https://en.wikipedia.org/wiki/USDC_\(cryptocurrency\)) before finding the form that worked. The first USDC white paper was mostly wrong. The second was mostly right. Coinbase came in as the first partner and co-founders of the CENTRE Consortium, the governance body that launched USDC in 2018 (and later closed in 2023). Regulatory clarity took seven years. The market cap did not move meaningfully until 2020. Sean describes all of this without apology — not as a series of failures but as the only honest way to climb a mountain when you cannot yet see the path.

USDC is now one of two stablecoins with genuine liquidity at scale. That fact contains, for Sean, both the vindication of the original thesis and its next unsolved problem. A world with two liquid stablecoins works. A world with ten thousand — each slightly different in value, each claiming to be a dollar — breaks the most basic property that makes money useful: that a dollar is always worth a dollar. This is the well-known [singleness of money](https://www.bis.org/publ/bisbull73.pdf) problem, and Sean thinks it is the largest single obstacle standing between where stablecoins are today and where they need to go.

His new company, [Catena Labs](https://catenalabs.com/), is built on a related inversion. Every financial institution in existence has spent years and enormous resources keeping bots out of its system. Catena is designed from first principles for a world in which bots — AI agents — are the intended customers. The compliance infrastructure, the identity layer, the policy engine: all of it is built not to exclude automated actors but to let the right ones in, safely, with cryptographic enforcement rather than human oversight at every step. Sean believes that within a foreseeable horizon, every financial transaction will be executed by AI. The question is not whether to build for that world but how to build for it without repeating the gatekeeper mistakes of the early internet.

In our conversation, Sean walks through the composing and coding parallels that have shaped how he builds, the slow series of ‘aha’ moments that led from Bitcoin to USDC, why the singleness of money matters more than most people in the stablecoin space acknowledge, and what it actually takes to build a financial institution whose customers are agents. He also explains why the hardest problems in both crypto and AI are not technical — they are about getting people who do not normally talk to each other to agree on the same approach before the window closes.

You can find Sean and the team at [@psneville](https://x.com/psneville) and [@catena\_labs](https://x.com/catena_labs). Follow the agent identity work on [Catena Labs’s website](https://catenalabs.com/).

![](https://substackcdn.com/image/fetch/$s_!ZBZf!,w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F010d52ed-26e6-4bce-a1a7-124fa5e09a6c_3840x264.png)

#### “Composing music for ensembles and building software to run on machines share a great many parallels.”

> ***Marieke: Welcome to Currency of Power, Sean. It’s a real pleasure to have you here.***

**Sean:** It’s a pleasure. Great to see you, Marieke and Nicolas.

> ***Marieke: Let me start with a bit of context. Nicolas and I started*** **[Currency of Power](https://www.currencyofpower.co/)** ***almost a year ago. What we try to do is examine the intersection of money, power, and technology. Very few people sit at the centre of all three, and Sean, you do. We are going to explore stablecoins, agentic payments, and how you think about the future of money. You have built many companies in this field and have always been good at reading the forces coming together, so it is really exciting to have you with us.***

**Sean:** Thank you.

> ***Marieke: For our audience: Sean is the co-founder of [Circle](https://www.circle.com/), inventor of [USDC](https://www.usdc.com/), and today the founder of [Catena Labs](https://catenalabs.com/), where you are building what you call an AI-native financial institution. I had the pleasure of working with Sean and Jeremy at Circle about ten years ago. Sean, you are a very deep thinker and you connect dots that many people miss, so hopefully you can bring clarity to some very complex topics today.***
> 
> ***Our conversation has three main parts. First, your career and mental models — from music and coding to building platforms and now AI-agent commerce. Second, the stablecoin revolution — what USDC revealed about money and programmable finance. Third, AI agents and agentic payments.***
> 
> ***Let’s start with your journey. You are a musician and an excellent coder. Tell us about that.***

**Sean:** On the music side, I would say I am much more a composer than a performer. I have always felt that composing music for ensembles and building software to run on machines share a great many parallels.

From the outside, people imagine you have an idea, you put together a plan, and then you go build it. But in music and in software it is more holistic than that. You have an idea — or an obsession you cannot set aside — but you do not always know exactly how it will be realised. So you cannot write a perfect plan and simply execute it. It is a little like building a house not from a blueprint, but by laying a bit of the foundation, then trying a bit of the roof, seeing what happens, learning things, and finding how the pieces connect. You work iteratively, and ultimately things come together to realise the core vision — though likely not in the form you first imagined.

In music, especially improvisational composition, you have to listen to everyone else playing. It is not a solo enterprise. And in all the best things I have built in software, it has been exactly the same: multiple players, internal and external.

From a career perspective, the conventional wisdom is to pick a lane, learn a domain, and stay dedicated to it. If you look into other lanes, you risk being criticised for drifting. I have always thought that is nonsense. It is far more productive to develop a sense for how builders in different domains work, and then try to connect those things. That is the only way I know how to do it, and to whatever extent I have been successful, it is the only way I could have done it.

> ***Nicolas: Does that mean you have been active in both music and technology simultaneously, or did you make a switch at some point?***

**Sean:** I have always done both at the same time, but I always knew I would be a software engineer — that building software products was what I would do. And the best way to build certain products is to build companies, and the best way to build generational platforms is to build several companies. So it cascades.

I never had it in my head that I would go full-time as a professional composer or performer. I scored some films, games, and commercials on the side and kept that up. But Jeremy and I founded Circle in September 2013, and as we ramped up, the music — and the other things I was doing — had to diminish because there are only so many hours in a day. I was teaching one class at [Berklee College of Music](https://www.berklee.edu/) at the time, and that was when things started to pull in different directions.

> ***Nicolas: Did you train in jazz?***

**Sean:** My mother was a professional classical musician — a flutist. My sisters and I grew up around formal music training. My biological father also played jazz and other things, so we studied everything. I was always drawn to ensemble music, which is where jazz sits. Berklee is known as a jazz school, though it covers every genre.

The trick with improvisation is to lean on a solid understanding of theory without letting it cloud your ear. You have to play in the moment, find the right pocket, listen to the other players, and let what you hear inform your playing — without it becoming an academic exercise, which is what it sounds like when it does not work.

> ***Nicolas: You also need a high level of technical mastery to translate what is in your head into actual notes.***

**Sean:** That is right. Growing up with a parent who was a professional performer, I saw from a very early age the hours required to reach that level. That is one of the reasons I knew I was not going to spend my hours on performance. My mother taught at collegiate level during the school year, practised her own repertoire, and did orchestral tours in the summers — fourteen to sixteen hours a day. The truism she lived by was something like: if I miss one day of practice, no one in the audience will hear it, but I will. If I miss two days, everyone in the band will hear it. If I miss three days, the audience will start to hear it. It is the consistency that matters to stay at that level.

There are so many musicians, but also people who study philosophy — Jeremy, my co-founder at Circle, studied political science. A lot of liberal arts people were building the early web. I think there is a resurgence of interest in those studies now in the age of AI. Those who orchestrate agentic workflows most effectively often have some skill, if not formal training, in literature, philosophy, or languages.

> ***Marieke: Walk us through your journey into coding. You founded Code Studio in 1998 and then moved through Macromedia and Adobe to Circle. What was that path?***

**Sean:** For me, there was always something I wanted to build, and so I would learn enough to build it, and hopefully find people along the way who could help teach me how. I coded since I was a kid — back then you could write out a program, send the raw source code, and have it published so that other people could copy it into their computers. I did that as a child.

I became more obsessive about it in my early teens. I was obsessive about music too, but I always had a sense I was going to build software because those were the things I was most interested in. And when computers began to be networked — not just software on my machine that I could give you the source code to, but all of our machines connected through shared protocols — I was solidly on that trajectory. None of us foresaw everything that would be possible on a worldwide web, but we had a sense of the enormous unlock that would come from networking machines on open standards that no single company owned.

It was not a matter of deciding to become a professional software engineer and majoring in computer science. It was more that I had things I wanted to build, I would go build them, and that would lead to the next thing. I was fortunate to meet very like-minded people along the way. Some of it was pushing the boulder uphill, but a lot of it was also a snowball rolling downhill, gathering momentum as we built.

> ***Nicolas: You mentioned open protocols — foundations that are not owned by anyone, things that anyone can build upon. Is that a common thread from those early days to crypto?***

**Sean:** It is. Before I started my first company, a lot of people used online services like [America Online](https://www.aol.com/), [CompuServe](https://en.wikipedia.org/wiki/CompuServe), or Prodigy. For most people it seemed like there was more content inside those walled gardens than on the open internet. The web was just emerging, and mostly it was a way to retrieve documents if you were in academia. A typical user paid a monthly fee for the privilege of sending email to someone else on the same service — you could not send it externally. Content was caged inside those platforms.

The premise of the internet was breaking through all of those walls. No longer controlled by gatekeepers, whether for content, for expressing your opinion, or for commerce. Open rails as a fundamental public good for the world.

And then when it came to crypto, the idea was: we played a small part in developing public goods for the exchange of content and data. Can we do the same thing for money? Because money was still very much locked behind gates. Gatekeeper business models are typically: I will give you access to the system, but I will take a little of your data — or your money — for the privilege of connecting. We looked at cryptography as a way to break that down in a very similar way.

---

#### “Bitcoin was a new thing on the whole, but its pieces existed before.”

> ***Marieke: What was your moment of conviction for crypto? In 2013, it was portrayed in the press as something for fraudsters and drug dealers. What did the ‘aha’ moment look like for you?***

**Sean:** There is still criticism of crypto, and the speculative side still ends badly for people. But there is also a lot of good that has been unlocked along the way.

For me there was not one single ‘aha’ moment — there was a series of them. Early on, it was conviction not necessarily around Bitcoin itself, but around that early combination of technologies. Bitcoin was a new thing on the whole, but its pieces existed before. It was a very clever connection of existing technologies to give people control of money flows. Seeing that it was possible to trust financial transactions without trusting your counterparty — trusting the software rather than the human beings or businesses built on top of it — that was an early one.

We founded Circle in 2013, but I did not write the USDC white paper until 2017, so it was four years. You could ask why we did not simply put dollars and euros and pesos on the internet from the start. The truth is it was a series of aha moments and experiments. Our overall vision has not changed — I think of it as a mountain in the distance that we are going to climb. We are not going to choose a different mountain. But the path to get there will almost certainly change as we learn things. You may need to backtrack and find another way, but the mountain is the same: to democratise access to global finance and create new ways for everyone around the world to engage with the economy on equal footing.

> ***Marieke: From where I sat at Circle, it felt like there was always this idea that money would be completely transformed — but that finding the path required constant adjustment. What were some of the testing moments?***

**Sean:** There were many. Even with USDC, the first version was not right. We had envisioned something almost like a programmatic central bank, with a unit called a cent, overseen by what we called the Centre consortium. It was a different mechanism for bringing fiat currencies on-chain, but it was not the right approach at the time. We revised it substantially, and it was really the second version that we took to market with Coinbase as the first major partner.

And I certainly did not do it unilaterally — there was a whole team of people involved.

More broadly, when you have a large vision for what you hope will be a generational platform, there will inevitably be multiple products that try to get you there. We did not follow the conventional startup wisdom of doing one thing, focusing on one ideal customer profile, finding their pain point, building a painkiller. We started with several possibilities: a consumer product called Circle Pay, a product called Circle Invest, an internal OTC trading desk, a treasury and trading function. Some experiments flat-out did not work — the first version of USDC was simply the wrong approach. Others worked for a period and then stalled, which is actually the hardest situation, because you are always asking whether to give it more time, invest more, or redirect resources. And then there were things we had firm conviction in that were not immediately successful.

USDC was one of those. When we launched, interest rates were low — the business model depended on interest rates — and we also knew that encoding a dollar token on internet rails would require legislation. I thought that might take ten years. It took seven: we got the GENIUS Act passed. Because of all of this, the market cap for USDC did not really begin to grow until mid-to-late 2020.

The hardest part of all of it, though — the most testing moments — is people. The most valuable technical problems to solve are always, at their core, people problems. Partners, customers, and the people inside the company who joined at the early stages and committed a portion of their professional lives to the vision. Managing course corrections with those people is a real challenge.

---

#### “A stablecoin is, at its core, just a dollar made to work on internet rails.”

> ***Marieke: Maybe we can move to stablecoins specifically. Stablecoin 101: what is a stablecoin, why is it called that, and what led Circle to create USDC?***

**Sean:** I will preface this by saying I have never loved the word stablecoin — I will explain why in a moment.

The concept is fairly simple. The idea is to take something like a US dollar — it can be other currencies, but when people refer to stablecoins they are mostly talking about dollars — and put it on internet rails so that it can be transferred not through credit card systems, wires, or other traditional rails that flow through banks, but directly across the internet. The advantage is that you can send money across borders almost instantly for almost no cost. The internet does not distinguish between a trillion dollars and one dollar in terms of data size — it is just a very slight difference in the data. It is not based on the value of the number.

The idea is simply to take money, make it accessible on open public-standard rails, and let businesses and individuals transfer value over those rails without intermediaries taking a cut along the way. If I send you a thousand dollars, you receive a thousand dollars. That sounds obvious, but in reality, depending on where you send it, a thousand dollars might arrive as eight hundred. Or nine hundred and ninety-seven. The internet largely wants data to be free, with other business models supporting that freedom. A stablecoin is, at its core, just a dollar made to work on internet rails.

More technically: the mechanism is that a dollar recognised by the government is deposited somewhere — in a bank account or equivalent. If you want to convert it into a dollar that works on the internet, that dollar goes into what are called reserves — a safe backing — and in return you receive a token, almost like a coat-check card. You can pass that token to someone else, but it is backed by the real thing. And the backing matters enormously. If the custodians are untrustworthy or the reserves are invested in risky assets, then you may think you hold a dollar but it is no longer backed by anything that can confirm that.

So fundamentally, a stablecoin is a fiat currency held in a trusted, risk-managed reserve, represented as a token that can circulate and later be redeemed for the underlying currency.

The word stablecoin has nothing to do with any of that. It is really a reference to crypto. The problem with crypto — the benefit if you are an investor, but the problem if you are making payments — is volatility. Bitcoin, Ethereum, Solana: all go up and down. If you want to buy a coffee, it is difficult to use something whose value could fluctuate by orders of magnitude in hours or days. Stablecoin simply means: compared to crypto, the value does not fluctuate. A dollar is a dollar is a dollar.

Outside the bounds of crypto, when you are just thinking about money, it is a slightly odd term.

> ***Nicolas: Going back to open protocols: there are protocols like SMTP for email and HTTP for the web. No such thing existed for money. In Europe, the SEPA system lets people send money from one country to another seamlessly and for free. It is very difficult for stablecoin advocates in Europe to make the case that we need them. Can you explain that difference?***

**Sean:** Good point on standards. HTTP for the web, SMS — no one owns those protocols. Google does not own HTTP. Microsoft does not own SMS. These are open protocols maintained by standards organisations in a way that has been beneficial to everyone, so that you can put your business online and anyone can interact with it without needing a special way in. That is a lot of the idea behind blockchains for moving money.

Now, for stablecoins specifically: the clearest way to help people understand the value is usually through two use cases.

The first is sending money across borders. The internet has no borders. If I send you an email, it does not stop at a border and wait a few days. But that is essentially how money works across borders. Treasury managers often do not know where their money is at a given point in time because it is in transit between accounts held overseas by custodians in different banks. The power of sending money over blockchains is full transparency at all times — an open, auditable ledger. And fees, while they vary by chain, are very small relative to the traditional system.

The benefit varies depending on which borders you are talking about. Sending sterling from London to a family in the Philippines — the problem is obvious. Sending money from Scotland to England — much less of a problem. But the idea is you should not have to think about borders at all.

The second use case is on the recipient side. Many people simply want to hold value they can trust and use in their own economies, and they cannot. It could be a lack of liquidity, inflation, or local currency problems. One of the reasons stablecoins largely mean dollar stablecoins rather than other currencies is that many people abroad want to hold dollars. They are not asking for stablecoins — they are asking for dollars, but they cannot open an account at a US bank. The best way for them to access dollars, whether as individuals or businesses, is through stablecoins.

> ***Marieke: How do you think things will evolve? There is fragmentation: central bank digital currencies, tokenized deposits, stablecoins. And today, ninety-nine per cent of stablecoins are in dollars. What is the place for other currencies and other forms of tokenized money?***

**Sean:** There is a third use case worth mentioning that is more interesting to people with an economist’s bent, and it was really foundational to Circle: the concept of a narrow bank, and what is sometimes called the Chicago Plan.

Narrow banking is a boringly simple concept. If I put money into a bank and come back ninety days later, my money is still there. That is not really how banking works today. Banks lend out a multiple of what you have deposited — fractional reserve lending — which is how most money is generated. Narrow banking asks: what if we had a bank that could not do that, or simply did not? It separates the money-creation function from the payment function.

Further experiments have explored: if deposits can only be invested in the most conservative, liquid instruments — short-term US treasuries, for instance — and there is some return on that, could depositors actually access some of it? The bank takes a margin because it needs to make money, but could depositors see some of the yield?

Such a narrow bank, accepting deposits directly and connecting to the Fed and to treasuries, is not legal in the United States. But stablecoins are effectively that in spirit. The reserves, now encoded in legislation like the GENIUS Act, must be very conservative — US T-bills, cash, highly liquid instruments with built-in consumer protections. No fractional reserve lending. You put your money in; it is still there; and to the extent it is invested, it goes into the most liquid and conservative instruments available.

When it comes to other currencies: the desire is not really for USDC or other dollar stablecoins. It is for dollars. And the real hurdle for any stablecoin — dollar or otherwise — is achieving meaningful liquidity. That depends on how desirable and trustworthy the underlying reserves are, and what incentives you can use to encourage people to hold and use the coin.

Prior to last year, I would say the biggest hurdle for stablecoin adoption outside crypto capital markets was simply regulatory uncertainty. It was not clear whether a stablecoin was an investment, a money market fund, or a payment instrument. Now it is much clearer. The next hurdle for anyone creating a stablecoin is liquidity. Technically, creating a stablecoin is easy. But why would anyone accept mine if there is no meaningful liquidity behind it?

The fundamental business model is still tied to interest income on the reserves. If interest rates are unhealthy, other alternatives begin to emerge — tokenized deposits and so on. That is a key consideration for the entire space.

Hi **letiauri@stanford.edu**

## Listen to this episode with a 7-day free trial

Subscribe to Currency of Power to listen to this post and get 7 days of free access to the full post archives.

[Already a paid subscriber? **Switch accounts**](https://substack.com/sign-in?redirect=%2Fp%2Fstablecoins-were-just-the-beginning&for_pub=eurostablewatch&change_user=true)