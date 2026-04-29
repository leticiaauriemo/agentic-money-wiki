---
title: "Post by @Bankless on X"
source: "https://x.com/bankless/status/2048057340356595775?s=46"
author:
  - "[[@Bankless]]"
published: 2026-04-25
created: 2026-04-26
description: "x402 broke a million transactions in the last two weeks alone, as endpoints keep going live across the ecosystem. Yet, a number of them app"
tags:
  - "clippings"
---
x402 broke a million transactions in the last two weeks alone, as endpoints keep going live across the ecosystem.

Yet, a number of them appear to be unauthorized wrappers of services whose terms EXPLICITLY prohibit reselling. Right now there's no way to tell which is which.

Three cases to consider:

\- Wolfram Alpha prohibits "resellers and aggregators," bans scraping, and bars sublicensing without permission. Yet, there's a third-party endpoint available for accessing it via x402

\- Amadeus, a travel service, requires formal certification for any third-party connection, documented in a Service Order. You can access via Stabletravel. Whether the endpoint meets that standard isn't visible from the outside

\- A third-party wrapper was sourcing Google Flights data via SerpApi — a company Google is actively suing for scraping Search results and reselling access. Endpoint was recently removed from the Agentic Market storefront

To be clear — the accountability here does NOT sit with x402. It's an open protocol, same as HTTP. It sits with those packaging unauthorized endpoints and collecting fees. With these current dynamics, providers bear the server load and see NONE of the revenue.

A cleaner model already exists. MPP marks first-party integrations directly on each service card. Exa announced native x402 support, going first-party and citing the Linux Foundation's governance as the reason for choosing it.

If there's no accountability here, it poisons the well. Potential native integrators become adversaries rather than participants. That revenue belongs to the providers. Native integration is how they claim it, and how x402 earns the legitimacy it needs to grow.

> **David Christopher @davewardonline** · 2026-04-25
> 
> ![Article cover image](https://pbs.twimg.com/media/HGwb9zxaQAIDdyX?format=jpg&name=large)

---

## Comments

> **Ledgerless @beledgerless** · [2026-04-26](https://x.com/beledgerless/status/2048462423406035021)
> 
> Service directories are genuine steps, but provenance is still asserted: by the directory operator marking it, or by the provider declaring it. The endpoint itself can't prove authorization to the agent calling it.
> 
> The architectural version of this is whether authorization could

> **Dave Burrells @dburrells** · [2026-04-26](https://x.com/dburrells/status/2048473510222193145)
> 
> Bankless nailed the tension , 1M tx proves rails work, but permissioning lags. Exa’s first-party + Linux Foundation move is the encouraging signal. This inflection decides: fast wrappers or trusted, verifiable ownership? My full strategic view 👉
> 
> > **Dave Burrells @dburrells** · 2026-04-26
> > 
> > x402 just crossed 1M transactions, proof programmable access markets are scaling fast. Demand is real. Rails work. Developers want composable, pay-per-use endpoints 👌
> > 
> > Yet the core tension remains: who captures the value? 🤔
> > 
> > Wrappers accelerate adoption but risk misalignment. x.com/Bankless/statu…

> **XyncPay @XyncPay** · [2026-04-26](https://x.com/XyncPay/status/2048190568585445628)
> 
> There's a real difference between wrapping someone's API and routing payments to it. Wrappers republish a service. Translation and settlement layers move value from agent to actual provider. The first creates accountability gaps, the second resolves them. Both can ship on x402.

> **Grok @grok** ·
> 
> Introducing the fastest video and image generation experience. Try SuperGrok today.