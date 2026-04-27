---
title: "Get Started with BVNK"
type: summary
topic: agentic-money
source_type: company-blog
tags: [stablecoin, infrastructure, compliance]
sources: ["Get started with BVNK.md"]
created: 2026-04-26
updated: 2026-04-26
---

# Get Started with BVNK

**Source:** BVNK Documentation, docs.bvnk.com/bvnk/get-started
**URL:** https://docs.bvnk.com/bvnk/get-started/get-started-w-bvnk/
**Published:** 2026-02-05

Developer onboarding documentation for [[bvnk]] — enterprise stablecoin payments infrastructure.

## Five-step onboarding process

1. **Contact Account Manager** — schedule kick-off to discuss requirements and integration approach
2. **Design implementation** — decide on delivery model (Managed vs Self-managed/Layer1); define payment flows, fees, fee schedules; find the right use case
3. **Create sandbox account** — test environment mirroring production with virtual funds; configure API keys, webhooks, wallets
4. **Integrate with BVNK services** — API reference for all BVNK functionality; wallets supported: Metamask (ETH/USDT ERC20), TronLink (TRX/USDT TRC20)
5. **Go live** — contact Account Manager to activate; note: sandbox config does NOT auto-transfer to live account

## Two delivery models

| Model | Description |
|-------|-------------|
| **Managed** | BVNK handles licensing, custody, and compliance-first approach |
| **Self-managed (Layer1)** | Bring your own licenses, custodian, liquidity partners; BVNK as layer underneath |

## What the sandbox enables

- API integrations testing with virtual funds
- Webhook configuration for real-time event notifications
- Customer account creation + KYB onboarding (Embedded model only)
- Crypto wallet creation
- Payment send/request
- Transaction reports
- Customer/contact management

## Integration prerequisites (for live)

- API keys configured in live environment
- Webhook URLs active
- Transaction limits verified for operational needs

## Significance

The BVNK docs illustrate the enterprise sales motion: no self-serve sign-up — gated by Account Manager. This is consistent with BVNK's positioning as infrastructure for 4,600+ institutional customers processing significant volume, not a developer-focused self-serve product.

## Related pages

- [[bvnk]]
- [[enterprise-stablecoin-payments-bvnk]]
- [[stablecoin]]
- [[mastercard]]
