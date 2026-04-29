---
title: "Who Authorized This? The Gray Area of x402"
source: "https://x.com/davewardonline/status/2048049242787213330"
author:
  - "[[@davewardonline]]"
published: 2026-04-20
created: 2026-04-26
description: "x402 needs native integrators to succeed. Unauthorized wrappers could turn potential partners into adversaries instead.From Mindshare's week..."
tags:
  - "clippings"
---
![Image](https://pbs.twimg.com/media/HGwb9zxaQAIDdyX?format=jpg&name=large)

x402 needs native integrators to succeed. Unauthorized wrappers could turn potential partners into adversaries instead.

From Mindshare's weekly newsletter (signup here: [bankless.com/mindshare](https://bankless.com/mindshare))

This week, Coinbase launched [agentic.market](http://agentic.market/), a storefront surfacing x402 endpoints to make the ecosystem more discoverable.

Browse it and you'll find live, metered access to a wide range of services, from onchain tools to mainstream APIs. Some endpoints are offered directly by the original provider. Many arrive via third parties: companies wrapping existing APIs in x402 (and/or MPP) and packaging them as agent-ready toolkits, accessible through a single connection for a small fee.

That second arrangement complicates things. Among those third-party-originated endpoints featured on Agentic Market are services for [Wolfram Alpha](https://agentic.market/?chart=payment-volume&service=products-wolframalpha-com), Google Flights, and [Amadeus](https://agentic.market/?service=developers-amadeus-com), a widely-used travel data platform. I focus on these three because none of the platforms have themselves announced an x402 integration, and their terms of service make it unlikely they've authorized a third party to build one on their behalf.

Every endpoint indexed on Agentic Market can either be **first-party** (the original provider offering their own API directly), **third-party authorized** (a reseller with explicit permission, usually through a formal certification or partnership program), or **third-party unauthorized** (a company reselling API access it pays for without permission to do so).

Across the marketplace, and the entire x402 ecosystem overall, there's no way to immediately tell which is which, with many seemingly falling into that last bucket.

> Apr 20
> 
> Introducing Agentic(dot)Market, the homepage of the agent economy. - Monitor agentic commerce trends - Discover services for your agent to buy - Sell your services to agents Thousands of services. Zero API keys. Powered by x402.

## What the Contracts Say

As mentioned, these three providers' terms make unauthorized third-party arrangements appear likely, and in some cases rule out other setups entirely.

**Wolfram Alpha** [explicitly prohibits "resellers and aggregators,"](https://products.wolframalpha.com/api/termsofuse?utm_source=chatgpt.com) bans scraping or data mining by any means, and bars selling or sublicensing the service without permission. The terms don't appear to leave room for an authorized third-party path at all. And, when looking at the endpoint's [Quick Start guide](https://agentic.market/?service=products-wolframalpha-com), it's clear this is not a first-party integration.

![Image](https://pbs.twimg.com/media/HGwXXyKbwAAsc5H?format=jpg&name=large)

API Prohibitions in Wolfram Alpha's Terms of Use

**Amadeus**'s [Master Subscription Services Agreement](https://www.amadeus-hospitality.com/legal/mssa/eng/?utm_source=chatgpt.com) grants customers access strictly for internal business purposes and prohibits any attempt to "rent, lease, distribute, sell, resell, assign, or otherwise transfer" their access rights. Any third-party connection requires certification by Amadeus, documented in a formal Service Order, meaning that's the only route to third-party authorized status, and whether any current endpoint meets it isn't visible from the outside.

![Image](https://pbs.twimg.com/media/HGwXeDIaoAIujkD?format=jpg&name=large)

Restrictions in Amadeus's Master Subscription Services Agreement

**Google** is the sharpest case. Google Flights has no public API, and Google protects its data aggressively.

Yet, a [third-party wrapper](https://agentic.market/?chart=buyers-sellers&service=www-google-com) is packaging access to Google Flights data, [sourced via SerpApi](https://stabletravel.dev/llms.txt) - [a company Google is actively suing](https://www.searchenginejournal.com/google-files-dmca-suit-targeting-serpapis-serp-scraping/563847/?utm_source=chatgpt.com) for scraping Search results and reselling access to them. Google's complaint alleges SerpApi built tools to bypass access controls, sends "hundreds of millions" of artificial requests per day to scrape, and resells copyrighted content embedded in Search.

So, Google is suing SerpApi for reselling copyrighted content and bypassing their access controls. At the same time, SerpApi is having its service wrapped by an [agentic toolkit provider](https://stabletravel.dev/llms.txt?ref=bankless.ghost.io) who’s providing it to agents and collecting fees for that provision. Food for thought.

![Image](https://pbs.twimg.com/media/HGwbZXjbkAAsV7n?format=jpg&name=large)

Details for SerpApi access via StableTravel endpoint

**What Compliance Looks Like**

It doesn't take a legal expert to see these dynamics are "tricky." The good news is that a cleaner model already exists.

MPP, the agentic payments protocol Tempo launched alongside its mainnet, shipped with 100+ compatible services on day one. Providers that integrated MPP directly - Parallel, Stripe Climate, Browser Base, and others - are [marked with a green circle](https://mpp.dev/services) on their card, showcasing first-party status.

![Image](https://pbs.twimg.com/media/HGwbqA-agAEFlP6?format=jpg&name=large)

Services Directory via [mpp.dev](https://mpp.dev/)

[Two(ish) weeks ago](https://x.com/ExaAILabs/status/2041562072027427265?s=20), Exa, a popular AI research tool, announced native x402 support across its search and contents endpoints - going first-party, partnering with Coinbase, and citing x402's governance under the Linux Foundation as a reason for choosing it over a proprietary route.

> Apr 7
> 
> We're excited to partner with @coinbase to enable agents to natively pay for web search, via x402! x402 is an open protocol that enables agents to pay via HTTP, governed by the Linux Foundation. When an Exa API request is made without an API key, Exa now returns a 402 status

## The Inevitable Outcome

Right now, whether a given endpoint is first-party, third-party authorized, or third-party unauthorized isn't visible from the outside. That's a solvable problem, and MPP's service directory - which makes the provenance of each integration legible - is a step in that direction.

Unauthorized scraping already strains providers in ways they can measure: server load, bandwidth costs, traffic they never agreed to serve. A third party wrapping that scraped data in x402 and collecting fees for it adds insult to injury. The provider bears the cost and sees none of the revenue.

It's worth being precise about where the problem actually lives. x402 is an open protocol - the same way any developer can build on HTTP, any developer can build on x402. The payment rail has no visibility into whether upstream data was obtained with authorization. The accountability sits with those packaging these endpoints for consumption.

If there's no accountability, it could poison the well for x402 broadly - turning potential native integrators into adversaries, rather than participants. That revenue belongs to the providers. Native integration is how they claim it, and how x402 earns the legitimacy it needs to grow.

**\*NOTE: as of Apr. 25th, Google Flights is no longer indexed on Agentic Market**