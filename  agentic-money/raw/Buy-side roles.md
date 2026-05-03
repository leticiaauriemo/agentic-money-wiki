---
title: "Buy-side roles"
source: "https://kyapay.org/overview/understanding-the-roles-in-kya/buy-side-roles"
author:
published:
created: 2026-05-03
description:
tags:
  - "clippings"
---
**Buyer Identity**: the aggregate verified identity of the buy-side entities, typically encompassing the Human Principal, the Agent Platform, and the Agent itself. This composite identity is conveyed via the KYA token, allowing the seller to verify the entire chain of responsibility behind a request, though specific use cases may require fewer or additional identity tiers.

**Human Principal** is the individual or business entity that initiates the purchase of a product or service and serves as the ultimate authority for the transaction. Sellers require the identity of the Human Principal (`bid`) to comply with KYC/AML regulations, accounting standards, and to maintain a direct customer relationship without disintermediation.

A **Buyer Agent** is the specific software process, or "machine identity," executing on behalf of the Human Principal. As these agents are dynamic and transient—capable of being launched, paused, and terminated frequently—they are typically identified by attributes like source IP addresses (`aid`) to allow independent verification by the seller.

**Buyer Agent Platform** The Buyer Agent Platform is the infrastructure or runtime environment hosting the Buyer Agent, such as a cloud provider or AI operator service. Its verified identity (`apd`) represents the business entity operating the platform, allowing Sellers to apply reputation-based logic or offer platform-specific service levels.