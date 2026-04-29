---
title: "Post by @0xCygaar on X"
source: "https://x.com/0xCygaar/status/2034689648023183524"
author:
  - "[[@0xCygaar]]"
published: 2026-03-19
created: 2026-04-25
description: "After doing some more digging into MPP from @stripe, here are my three favorite features of MPP that make it extremely powerful: 1) Session"
tags:
  - "clippings"
---
After doing some more digging into MPP from @stripe, here are my three favorite features of MPP that make it extremely powerful:

1) Session payments

One of the limitations of x402 is that you have to transact onchain for every single API call. This makes it slow and expensive if you want to make many calls in succession. With MPP, you can create a session, load in funds, and then make multiple API calls that get batched into a single payment. This will help agentic payments really scale.

2) Multiple payment methods natively supported

MPP allows clients to pay in stablecoins, Stripe cards, or evening Lightning Bitcoin. I'm personally a huge fan of stablecoin payments, but different API providers will have different needs. Allowing agents to pay in both crypto and fiat (via Stripe) will give MPP the highest chance of adoption amongst service providers. The native integration with existing Stripe infra makes onboarding frictionless.

3) Custom payment methods

Not only does MPP support the methods listed above, but you can easily extend it to support different blockchains, card processors, or proprietary systems. Several chains have already started building for MPP support (Abstract soon), but in general this will make MPP as flexible as possible for all vendors.

4) (Bonus) Leverages the existing 402 status code

This is not unique to MPP as x402 also does this, but it's really cool that we're building on top of a protocol spec (402 status code) that was written almost 30 years ago when the internet was first starting out.

![Image](https://pbs.twimg.com/media/HDynAVLXUAAycho?format=jpg&name=large)

---

## Comments

> **sweetman @sweetman\_eth** · [2026-03-19](https://x.com/sweetman_eth/status/2034729980056244502)
> 
> I have yet to see anyone give critique to MPP.
> 
> Seems like a pure upgrade from x402.

> **KeeperHub @KeeperHubApp** · [2026-03-24](https://x.com/KeeperHubApp/status/2036359665580171421)
> 
> Everyone's talking about x402 vs MPP. They're solving different problems, not competing. But here's the thing nobody's asking: once the agent pays, who makes sure the transaction actually lands? Wrote our take on this.
> 
> https://keeperhub.com/blog/006-mpp-vs-x402…

> **Jimmy Ashcot @ashcotXBT** · [2026-03-19](https://x.com/ashcotXBT/status/2034720782048530759)
> 
> session payments are the unlock if you want agent loops to scale

> **AltcoinAce @AltcoinAce\_X** · [2026-03-19](https://x.com/AltcoinAce_X/status/2034691873797820500)
> 
> interesting direction, but feels like success depends less on features and more on how invisible they can make the whole system for end users

> **Lina @XNXX\_EN** · [2026-03-19](https://x.com/XNXX_EN/status/2034703213405081643)
> 
> session payments gonna scale agents huge

> **0xMeow @0xMeow0130** · [2026-03-19](https://x.com/0xMeow0130/status/2034701439981977911)
> 
> Let’s open a lesson on this

> **Alexa Web3 (e/acc) @alexabelonix** · [2026-03-19](https://x.com/alexabelonix/status/2034695032973009251)
> 
> Session payments change the game

> **Alpha Batcher @alphabatcher** · [2026-03-19](https://x.com/alphabatcher/status/2034693181196181672)
> 
> session payments from the stripe, one of the favorite feature too

> **Nano micropayments @XNanoPayments** · [2026-03-20](https://x.com/XNanoPayments/status/2034845946312266182)
> 
> Just use @Nano ffs
> 
> Its that easy

> **Frank Salinas @frankjsalinas** · [2026-03-19](https://x.com/frankjsalinas/status/2034719594032869750)
> 
> Great summary.