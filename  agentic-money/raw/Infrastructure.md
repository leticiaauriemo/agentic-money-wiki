---
title: "Infrastructure"
source: "https://kyapay.org/overview/understanding-the-roles-in-kya/infrastructure"
author:
published:
created: 2026-05-03
description:
tags:
  - "clippings"
---
**Reverse Proxy** is an intermediary infrastructure on the sell-side, such as a Bot Manager, Application Firewall (WAF), or Load Balancer, that sits between the public Internet and the Seller Service. While traditionally designed to block automated traffic, in the KYAPay protocol, it acts as a gatekeeper that validates tokens (`kya`) to allow verified agentic traffic to pass while continuing to filter malicious bots.

The **Identity Token Issuer** is a trusted neutral entity that conducts Know Your Customer (KYC) and Know Your Business (KYB) verifications. It is responsible for issuing cryptographically signed "kya" tokens that attest to the identity of the Buyer Principal, Buyer Agent, and Buyer Agent Platform. Identity Token Issuer’s other responsibilities include:

- **Trust Anchor:** The Issuer maintains trust relationships with both Buyers and Sellers. To ensure broad interoperability, market participants may establish relationships with multiple Identity Token Issuers to find a common trust anchor for settlement.
- **Policy Enforcement:** The Issuer actively enforces Seller-defined access requirements at the point of token generation.
- **Field Requirements:** It adheres to the Seller's specifications regarding which identity fields are mandatory. If a Buyer has not verified the specific fields required by a Seller, the Issuer will refuse to generate the token.
- **Approval Gating:** It can enforce permissioning workflows in which the Issuer creates tokens only after the Seller explicitly approves the specific Buyer Agent.
- **Privacy and Scoping:** In scenarios involving intermediaries like bot managers, the Issuer can generate tokens containing minimal information (e.g., only Source IP addresses). This allows the intermediary to verify the legitimacy of the request source without exposing the Buyer Principal's Personally Identifiable Information (PII).
- **Operational Consolidation:** To reduce operational overhead, the protocol favors scenarios where a single Identity Token Issuer validates all three buy-side tiers (Principal, Platform, and Agent), rather than managing a complex web of distinct issuers for each tier.

The **Payment Token** Issuer is a trusted entity responsible for facilitating the exchange of payment intent and credentials between the Buyer and the Seller. It issues "pay" tokens that enable settlement via various schemes (Cards, Banks, Stable Coins) without exposing raw credentials insecurely. Payment Token Issuer’s other responsibilities include:

- **Credential Exchange and Tokenization:** The Issuer enables Buyers to share payment credentials securely. For traditional systems like Payment Cards, it tokenizes sensitive information (e.g., creating a virtual card number) to allow Sellers to "pull" funds without being exposed to raw financial data. For Bank-based payments, it enables the secure sharing of account information.
- **Settlement Facilitation:** The Issuer supports diverse settlement architectures (push, pull, and hybrid), issuing tokens that inform the Seller of payment status or provide the necessary data to execute the charge.
- **Trust and Interoperability:** Similar to identity, the Payment Token Issuer acts as a trust anchor with relationships to both Buyers and Sellers. Market participants may utilize multiple issuers to ensure compatibility across various payment schemes (Cards, Banks, Blockchain) and to find a common settlement method for a specific transaction.

**Onboarding:** The Issuer is responsible for facilitating the onboarding of Buyer Principals and Agents onto specific payment rails, enabling them to generate valid `pay` or `kya-pay` tokens for commerce.