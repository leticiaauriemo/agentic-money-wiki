---
title: "Understanding x402 and MPP in One Article: Two Routes for Agent Payments"
source: "https://www.rootdata.com/news/584290"
author:
published:
created: 2026-04-25
description: "Original Title: Stripe's MPP vs."
tags:
  - "clippings"
---
*Original Title: [Stripe's MPP vs. x402: What Actually Happened Today](https://defiprime.com/stripe-mpp-vs-x402)*  
*Original Author: Nick Sawinyh, defiprime.com*  
*Translation: Peggy, Blockbeats*

Editor's Note: Regarding the issue of how agents make payments, x402 and MPP provide two almost opposite paths.

x402 follows a minimal protocol: it embeds payments directly into HTTP requests, implementing pay-per-request in the simplest way. No accounts, no intermediaries, resembling the open, permissionless design of the early internet, suitable for long-tail developers and decentralized scenarios.

MPP, on the other hand, maximizes the system: it addresses high-frequency trading, risk control, and fiat currency access issues through sessions, streaming payments, and compliance frameworks. It does not pursue purity but prioritizes meeting real business needs, making it more suitable for enterprise-level and scalable applications.

The differences between the two are essentially two solutions to the same problem: whether to make payments a part of the protocol or a layer of the system.

Thus, they are not in complete competition but rather distributed across different ranges, with x402 covering the long-tail needs of the open network and MPP handling high-frequency and commercial traffic. In an agent economy that is yet to take shape, this differentiation may be inevitable.

Here is the original text:

HTTP status code 402 has been waiting for a purpose since it was defined in the HTTP/1.1 specification in the late 1990s. Its meaning is "Payment Required." The original idea was to embed payment capabilities into the protocol layer of the web, allowing machines to purchase resources like they request web pages.

However, this idea has largely not been realized. Over the years, this status code has only appeared occasionally in some edge cases, such as Shopify's rate-limiting responses and billing errors from Apple Mobile Me, but no one has truly built the micropayment future it implies. Instead, we have credit cards, subscription paywalls, and API Key mechanisms, all of which are essentially designed for human operators.

Today, this future has emerged with two competing implementation paths, both released on the same day. Next, I want to outline what they are, their differences, and why Stripe is betting on both routes.

### x402: A Simpler Solution

![](https://admin2049.chaincatcher.info/upload/image/20260322/1774149497443-513928.webp)

Coinbase officially launched x402 in May 2025, and its core idea can be described as radically minimalist. The client requests a resource; the server returns HTTP 402 and informs the client how much to pay, which token to use, and on which chain to complete the payment. After the client completes the payment on-chain, it attaches the payment proof to the re-initiated request, and the server then delivers the resource.

It's that simple. No account system, no API Key, and no subscription mechanism. Just a round trip of an HTTP request with a payment inserted in between.

Now, Stripe has provided native support for x402 in its payment system, allowing merchants to receive these payments directly through their existing backend. However, fundamentally, x402 is still a protocol led by Coinbase, governed by the x402 Foundation, which was jointly initiated by Coinbase and Cloudflare in September 2025. The protocol is fully open-source (Apache 2.0 license) and offers SDKs in multiple languages, including TypeScript, Go, and Python.

In terms of support, Coinbase's official documentation shows that it currently supports ERC-20 payments on Base, Polygon, and Solana. The ecosystem is also exploring extending it to other chains like Avalanche, Sui, and Near, but maturity varies.

Looking at adoption data, this part is a bit more complex. Coinbase states that x402 has processed over 50 million transactions through its Agentic Wallet infrastructure. It sounds impressive, but according to on-chain analysis data from Artemis cited by CoinDesk on March 11: the daily transaction volume is about 131,000, with a total amount of approximately $28,000, and the average payment per transaction is only about $0.20, with about half resembling testing or gamified behavior rather than real commercial transactions.

But this may not be a bad thing. Because this protocol was originally designed for a market that does not yet truly exist, a world where AI agents make micropayments (even below 1 cent) for API calls and data queries. And the merchants serving this market are just beginning to emerge.

For example, Google’s Agentic Payments Protocol (AP2, part of the A2A framework) has already integrated x402; Lowe's Innovation Labs showcased a demo where an AI agent can complete the entire process from product discovery and research to ordering in one flow. Meanwhile, World (initiated by Sam Altman) released AgentKit this week, adding human identification capabilities to x402 wallets.

The core assumption behind this is: as long as payments are made as lightweight as HTTP requests, application scenarios will naturally emerge. Whether this holds true remains to be seen.

### MPP: A Full-Stack Solution

![](https://admin2049.chaincatcher.info/upload/image/20260322/1774149498006-155639.webp)

Stripe and Tempo chose a different path. The Machine Payments Protocol (MPP) was launched today alongside the Tempo mainnet. Unlike x402, which serves as a lightweight encapsulation layer on existing blockchains, MPP is specifically designed for the high-frequency trading scenario of agents.

Its core mechanism is sessions. Unlike initiating an on-chain transaction for every resource request, agents can authorize a spending limit once and then continuously make micropayments within that limit. If you are an AI that needs to query thousands of data sources every hour, you definitely do not want to sign and broadcast an on-chain transaction each time, and sessions are designed to solve this problem.

The Tempo chain is also built around this need. It supports tens of thousands of transactions per second, has sub-second confirmation times, and does not have a native gas token. Users can directly pay transaction fees with stablecoins, eliminating the cumbersome step of needing to purchase some random token for transfers.

Another component worth understanding is that Stripe's Agentic Commerce Suite includes Shared Payment Tokens (SPTs). This is not part of MPP itself but is an extension mechanism from Stripe that can be used in conjunction. SPT allows agents to securely pass user credit card or wallet credentials to merchants without exposing real data. These credentials are limited to single transactions and have time constraints, which can be understood as a programmable, self-destructing authorization. In practical use, this means an agent paying through MPP can use USDC on Tempo or a user-linked Visa card, or even a combination of both.

According to the Tempo mainnet launch blog, its partners include Anthropic, DoorDash, Mastercard, Nubank, OpenAI, Ramp, Revolut, Shopify, Standard Chartered, and Visa. The Block reported that over 100 services were already available in the payment catalog at MPP's launch, including Alchemy, Dune Analytics, Merit Systems, and Parallel Web Systems. Matt Huang, co-founder of Tempo and Paradigm, stated in an interview with Fortune that this field is still in its early stages, and the design goal of MPP is to expand to more on-chain environments beyond Tempo in the future.

### Why Stripe Supports Both

If you are already integrated with Stripe, the most practical answer is: you do not need to choose between the two.

Stripe supports x402 and MPP through two independent integration paths rather than abstracting them into a unified interface. For x402, its documentation mainly covers the processes of generating recharge addresses, on-chain monitoring, and settling funds to Stripe accounts—you are responsible for returning a 402 response, while the underlying crypto payment infrastructure is handled by Stripe. Currently, it supports USDC on Base, with plans for future expansion. For MPP, merchants can receive session-based streaming payments through the same PaymentIntents API.

The Agentic Commerce Suite released by Stripe in December 2025 is built on these two payment tracks. Merchants only need to upload their product catalogs, select the AI agents they wish to integrate, and Stripe will handle product discovery, checkout processes, fraud prevention, and tax processing. Currently, URBN, Etsy, Coach, Kate Spade, and Ashley Furniture are already using it, and platforms like Wix, WooCommerce, BigCommerce, Squarespace, and commercetools have also completed integration.

Its strategy is quite clear: control the abstraction layer and allow the underlying protocols to compete freely.

### Comparison

From a macro perspective, both protocols are doing the same thing: enabling machines to pay for resources via HTTP. But the real differences lie in the details.

#### x402 (led by Coinbase) vs MPP (Stripe + Tempo)

**Standardization**  
x402: Fully open-source (Apache 2.0), driven by the x402 Foundation to encourage multi-party participation (Coinbase, Cloudflare, Visa, Google).  
MPP: Open standard, jointly established by Stripe and Tempo, part of the Stripe Agentic Commerce Suite.

**HTTP Mechanism**  
x402: Revives HTTP 402, initiates requests through the PAYMENT-REQUIRED header, and completes retries using PAYMENT-SIGNATURE.  
MPP: Also uses a challenge-response mechanism but employs the Payment HTTP Authentication Scheme (IETF draft), binding the challenge ID through HMAC.

**Payment Layer (Rails)**  
x402: Designed to be chain-agnostic, currently supports Base, Polygon, and Solana, with other chains still being explored.  
MPP: Based on the Tempo blockchain—a payment-optimized L1, supporting over 10,000 TPS, sub-second confirmations, and no native gas token; the long-term goal is cross-chain compatibility.

**Payment Methods**  
x402: Pure stablecoins, fully on-chain.  
MPP: Supports USDC on Tempo + SPT (Stripe's mechanism), enabling a mix of crypto and fiat (credit cards, wallets, BNPL).

**Settlement Methods**  
x402: Settled on-chain (approximately 200ms to several seconds), with facilitators like Coinbase responsible for verification and settlement.  
MPP: Tempo's sub-second confirmation, with Stripe automatically crediting and handling compliance.

**Merchant Integration**  
x402: Open-source middleware (Express, Hono, Next.js, etc.), can be self-built or use facilitators.  
MPP: Directly integrates with Stripe's PaymentIntents API, with risk control, tax, refunds, and reporting all built-in.

**Core Innovation**  
x402: Extremely simple, vendor-agnostic, akin to the Unix philosophy in payments.  
MPP: High throughput + fiat integration, achieving streaming payments, micropayment aggregation, and programmable spending control based on SPT.

**Key Partners**  
x402: Coinbase, Cloudflare, Google (A2A/AP2), Visa, World, Anthropic (MCP).  
MPP: Stripe, Visa, Lightspark, Anthropic, DoorDash, Mastercard, OpenAI, Shopify, Revolut, Standard Chartered.

x402 is more like the preferred solution when building an open system: independent developer APIs, decentralized data markets, or any service that does not wish to rely on payment processors. Its specifications can be written into a white paper, and integration only requires middleware and a wallet address. This purity is very appealing—though the limitations of pure crypto also mean its audience is narrower.

MPP, on the other hand, represents a completely different paradigm. If your agent needs to conduct hundreds or even thousands of transactions in a single session without wanting to go on-chain each time, it is the more reasonable choice. The session mechanism keeps most interactions off-chain until final settlement; Stripe's compliance system handles risk control and taxes; and the hybrid model of SPT allows agents to not be limited to stablecoins but also directly utilize user payment methods like Visa. It may not be as elegant, but it is more aligned with reality.

Interestingly, they are not entirely in competition. x402 covers long-tail open scenarios, while MPP covers enterprise-level high-frequency traffic. Stripe's strategy is also clear: it does not bet on a single protocol but ensures that regardless of which path wins, funds ultimately flow into Stripe's account system.

### Current Situation: Where Are We Now?

To be honest, there are currently almost no truly scaled transactions.

According to Coinbase's x402 release information, early partners include Hyperbolic (GPU inference payments) and Anthropic (MCP protocol integration). Stripe's blog mentions agent scenarios that pay per API call (e.g., CoinGecko). The Tempo launch catalog included over 100 services. Cloudflare's Agents SDK has natively supported x402, and some small projects on Base L2 are also trying to use x402 as a payment gateway.

But overall: transaction volumes are small, the number of merchants is limited, and most activities remain in the experimental stage.

This is not surprising. Any new payment infrastructure is like this in its early stages. The so-called partner list can sometimes have a significant gap between signing a letter of intent and going live, and these releases usually do not make a clear distinction.

What is more noteworthy is the heavyweight participants behind the infrastructure. Stripe processed $1.9 trillion in payments in 2025, with a year-on-year growth of 34%. Meanwhile, Coinbase, Cloudflare, Visa, Google, and the entire network of partners from Tempo have entered the scene.

In other words, the tracks have been laid. The only remaining question is: in 2026, will AI agents really need to conduct large-scale transactions on this track? Or is this more like laying fiber optics in 1998—demand has not yet arrived, but the infrastructure is ahead.

### Which One to Choose?

If you are building an open, permissionless system—x402 is the more natural choice. No need to register on a platform, no need to connect to payment processors; just import middleware and bind a wallet to receive payments. The trade-off is that compliance, risk control, and fiat settlement must be handled by yourself.

If you are already within the Stripe system and wish to tap into agent traffic—MPP is more suitable. Sessions, streaming payments, a mix of fiat and crypto, and a complete compliance system essentially represent a configuration upgrade rather than a system overhaul.

If you only care about one thing: regardless of which protocol the agent uses, I can still get paid. Then the answer is actually: use Stripe. It supports both sides.

HTTP 402 has finally found its purpose. It just waited for nearly 27 years.

[(Source)](https://www.chaincatcher.com/article/2253569)

### Recent Fundraising

[Robin Markets](https://www.rootdata.com/Projects/detail/Robin%20Markets?k=MTk3MzM%3D)

$470K Apr 24

[Fere AI](https://www.rootdata.com/Projects/detail/Fere%20AI?k=MTYwMDc%3D)

$1M Apr 24

[Voran](https://www.rootdata.com/Projects/detail/Voran?k=MjQzNjE%3D)

$3M Apr 24

### New Tokens

[MegaETH](https://www.rootdata.com/Projects/detail/MegaETH?k=MTA5NjQ%3D) MEGA

Apr 29

[Staynex](https://www.rootdata.com/Projects/detail/Staynex?k=ODc0Mg%3D%3D) STAY

Apr 22

[OpenGradient](https://www.rootdata.com/Projects/detail/OpenGradient?k=MTQzMzc%3D) OPG

Apr 20

### Latest Updates on 𝕏

Apr 24

Apr 24

Apr 24