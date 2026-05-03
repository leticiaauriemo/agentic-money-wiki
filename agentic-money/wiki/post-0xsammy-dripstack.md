---
title: "Post by @0xSammy on X — DripStack"
type: summary
topic: agentic-money
source_type: social
tags: [agentic-commerce, subscriptions, stablecoin]
sources: [Post by @0xSammy on X.md]
created: 2026-05-03
updated: 2026-05-03
---

# Post by @0xSammy on X — DripStack

**Source:** [@0xSammy on X](https://x.com/0xsammy/status/2050556363525230697), published 2026-05-01
**About:** Analysis and walkthrough of DripStack — a live demo of x402 + MPP for per-article Substack payments

## The headline claim

> "A trillion agents reading a million writers at a cent per article is a bigger market than the entire Substack subscription base today."

DripStack is built by Michael Blau (@blauyourmind). It indexes premium Substacks and charges $0.01 per article via either x402 on Base or MPP on Tempo — whichever the agent prefers.

---

## How DripStack works

1. **Catalog layer (free):** Agent queries the DripStack index for available publications and post titles — no payment required
2. **Article layer (paid):** Agent requests the full article body → DripStack returns an HTTP 402 response with payment instructions → agent pays $0.01 → article unlocks
3. **x402 path:** Agent hits the URL, gets USDC payment instructions, signs a transfer on Base, retries with receipt
4. **MPP path:** Same flow routed via Tempo's L1, settling on MPP rails
5. **Dual-rail support:** Writer gets paid regardless of which rail the agent uses
6. **Wallet:** Agent-owned; funded with USDC on Base; spends autonomously at $0.01/article

**Audit:** Spend can be verified on mppscan.com or x402scan.com

---

## Significance

DripStack is notable as one of the cleanest live demos of both protocols working in production, and one of the first real tests of whether per-call agent payments can replace subscription bundling for written content.

**The business model inversion:** Traditional Substack is a subscription paying for anticipated future value. DripStack is pay-as-you-read — every article has to be worth $0.01 on its own merits. For agents consuming content at scale, this could be far more efficient than buying subscriptions to dozens of publications.

**The risk:** "Agentic SEO" — providers gaming agent purchase decisions. Acknowledged by the author as a concern but not a dealbreaker.

---

## Related pages

- [[x402]] — one of the two payment rails
- [[mpp]] — the other payment rail
- [[merit-systems]] — operates mppscan.com and x402scan.com (audit tools used here)
- [[headless-merchants]] — DripStack is a headless merchant abstracting Substack paywalls
