---
title: "Machine Payments Protocol (MPP)"
type: rail
topic: personal-project
tags: [mpp, stripe, payment-rail, agent-payments, fiat]
sources: []
created: 2026-04-22
updated: 2026-04-22
---

# Machine Payments Protocol (MPP)

**Type:** payment protocol (Stripe, fiat-based)
**One-line:** Stripe's protocol for autonomous machine-to-machine payments — enables agents to pay for services using traditional fiat rails without human approval per transaction.

**TODO: expand**

## How it works

MPP provides the authentication, authorization, and settlement primitives agents need to pay for services programmatically. Unlike x402 (crypto), MPP runs on Stripe's fiat infrastructure — more palatable to regulated financial services clients.

## Agent-friendliness

High — designed for machine-native use cases on familiar Stripe infrastructure.

## Who controls it

Stripe.

## Our relationship

MPP is a strong candidate as our primary payment rail, especially for financial services clients who cannot use crypto rails. The fiat/crypto split (MPP vs. x402) may end up being a client configuration option.

## See also

[[x402]] — crypto-based alternative
[[stripe-mpp]] — company page

## Sources

*TODO: ingest Stripe MPP launch coverage*
