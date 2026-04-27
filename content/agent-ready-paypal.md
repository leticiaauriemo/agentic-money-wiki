---
title: "Agent Ready — PayPal's ACP Integration"
type: summary
topic: agentic-money
source_type: company-blog
tags: [agentic-commerce, wallet, payment-processor, identity-kyc]
sources: ["Agent Ready.md"]
created: 2026-04-26
updated: 2026-04-26
---

# Agent Ready — PayPal's ACP Integration

**Source:** PayPal Developer Documentation, docs.paypal.ai
**URL:** https://docs.paypal.ai/growth/agentic-commerce/agent-ready

Technical documentation for PayPal's implementation of OpenAI's Agentic Commerce Protocol (ACP).

## What Agent Ready does

Agent Ready transforms existing PayPal/Braintree merchant integrations to accept payments from AI platforms (starting with ChatGPT) without rebuilding the payment stack. It is PayPal's answer to the question: "how does a merchant get paid when an AI agent, not a human, is the buyer?"

## The Agentic Commerce Protocol (ACP)

OpenAI-developed open standard with three specs:

| Spec | Purpose | Integration |
|------|---------|-------------|
| **Product feed** | How merchants expose catalogs for AI discovery | OpenAI ↔ Merchant |
| **Agentic checkout** | How AI agents create checkout sessions + complete orders | OpenAI ↔ Merchant |
| **Delegated payment** | How AI platforms securely obtain payment credentials from PSPs | OpenAI ↔ PSP (PayPal/Braintree) |

## How it works

1. AI platform (e.g., ChatGPT) discovers merchant products via product feed
2. AI agent creates a checkout session via agentic checkout spec
3. ChatGPT requests a **delegated payment token** from Braintree
4. Braintree issues a **one-time-use payment nonce** bound to the specific merchant ID + amount + currency + expiry
5. ChatGPT sends the nonce to the merchant's MCP server as part of checkout
6. Merchant's `complete_checkout` MCP tool processes the nonce via existing Braintree integration

## The payment nonce

The key innovation: a **payment method nonce** is a secure, single-use reference to buyer payment info. It:
- Is bound to the merchant's specific `merchant_id`
- Has `max_amount` validation (transaction cannot exceed configured max)
- Has currency validation (must match transacting merchant's currency)
- Expires at a configured timestamp

This means the buyer's actual payment credentials never leave PayPal/Braintree — the merchant only ever sees a nonce.

## Technical integration

**Server (Python MCP tool):**
```python
@tool(description="Complete checkout and process payment")
async def complete_checkout(checkout_session_id, buyer, payment_data):
    token = payment_data.token
    result = gateway.transaction.sale({
        "amount": "10.00",
        "payment_method_nonce": token,
        "options": {"submit_for_settlement": True}
    })
```

**Transaction tracking:**
```python
result.transaction.facilitator_details.oauth_application_name  # => "ChatGPT"
result.transaction.facilitator_details.oauth_application_client_id  # => "oauth_client_abc123"
```

AI-initiated transactions are tagged with facilitator details for reporting.

## Significance

Agent Ready is PayPal's direct response to OpenAI becoming a payments surface. By integrating via ACP, PayPal ensures its 400M+ user payment relationships remain the settlement layer even when ChatGPT is the commerce interface. The one-time-use nonce model preserves PayPal's fraud protection and identity stack within the agentic flow.

## Related pages

- [[paypal]]
- [[agentic-commerce-services-paypal]]
- [[agentic-commerce-solutions-paypal]]
- [[stripe]]
- [[agentic-commerce]]
