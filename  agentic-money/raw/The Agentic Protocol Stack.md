---
title: "The Agentic Protocol Stack"
source: "https://kyapay.org/overview/the-agentic-protocol-stack"
author:
published:
created: 2026-05-03
description:
tags:
  - "clippings"
---
### Overview

Each protocol focuses on solving a specific area of the problem space, and each industry doesn’t look at the problem the same way, requiring different sets of protocols. While the publishing and media industry mainly focuses on licensing and being fairly compensated for its content, the e-commerce industry focuses more on safely enabling transactions with agents without opening the door to new fraud threats. Figure 1 provides insight into the problem space addressed by the various protocols and how they complement each other.

![Agentic Protocol Stack](https://s3.us-west-2.amazonaws.com/kyapay.ai/agentic-protocol-stack-300x169.png)

***Fig.1: Agentic protocols ecosystem***

- **Licensing**: a content license agreement that gives content owners the means to instruct agents on how content may be used and the potential costs of accessing it. This is especially important for media, publishers, online knowledgebases like wikipedia, or forums like stackoverflow This is what the Real Simple Licensing protocol is designed to solve.
- **Identity:** legacy methods of identifying and categorizing bots and agents based on HTTP header signatures or the networks they may originate from won’t scale in a world where thousands of independent developers regularly launch new agents to automate workflows or streamline online interactions. The KYA (Know Your Agent) and web-bot-auth protocols aim to help authenticate AI agents at scale. In a world where a platform may run multiple agents serving multiple purposes, KYA offers the most flexible protocol by identifying the platform and the agent independently, all backed by the extensive KYB (Know Your Business) or KYC (Know Your Customer) framework, which adds that extra level of trust. Different aspects of identity must be considered
- - **Platform identity:** identifies the platform running the agent, for example in the case of the ChaptGPT, the platform would be OpenAI
		- **Agent identity**: Agents can be ephemeral and come and go. Also, AI platforms may run several agents. The agent identity reflect the agent name and typically purpose
		- **User identity**: Agents tend to obfuscate the user principal they represent. Protocols like KYA aim to restore that transparency. The trusted agent protocol from Visa and Mastercard’s agent pay provides that visibility, too, to a lesser extent since the personal data is obfuscated.
- **Intent**: recording the user intent, for example, “buying a red shirt for less than $100,” is key to making sure the agent follows a predefined task and preventing dispute and fraud risk once a transaction is completed. KYAPay (an extension of the KYA protocol to support payments) and the verified intent credential used by Visa and Mastercard offer the same functionality as specified in the AP2 protocol from Google.
- **Payment**: key to completing any commerce transaction, the various protocols proposed offer roughly the same flexibility across payment methods, including credit cards, bank transfers, and cryptocurrencies.
- **Agent communication and discovery**: In a not-so-distant future, we may see the emergence of specialized agents that communicate with each other to complete the various tasks of a transaction. For example, a generalist travel agent might delegate different parts of a trip to agents specializing in hotel bookings, flight bookings, and activities. The A2A protocol is seen as the yellow pages of agents and helps find the relevant one to complete the various tasks and organize communication between them. An agent receiving a task from another agent may leverage protocols such as KYA and webbot-auth to authenticate its peers.
- **Site API discovery**: Agents may learn to discover the various APIs available on a site to run various functions but would rather have access to a dictionary that lists them with their functionality. The widely adopted model context protocol (MCP) is designed to help achieve this goal.

Rather than a single "winner-take-all" standard, the agent commerce landscape is evolving into three segments, each optimized for a specific type of interaction:

1. **The Light-Weight Rail (X402/H402):** The "Vending Machine" layer for anonymous, frictionless, and instant micropayments.
2. **The High-Assurance Rail (AP2, ACK):** The "B2B Purchase Order" layer for complex, regulated, and contract-heavy procurement.
3. **The Relational Rail (KYAPay):** The "Secure Checkout" layer for everyday, identity-linked commerce—enabling the accounts, subscriptions, and relationships that drive the majority of real-world business.

#### Understanding the Foundation of the Agent Economy

The agent economy is built on two primary axes: vertical integration (how agents use tools) and horizontal collaboration (how agents work with each other). For either to function, there must be a standard for communication and a corresponding standard for verifying identity.

1. #### The Protocols Powering the Two Axes

[**Agent-to-Tool: Model Context Protocol (MCP)**](https://modelcontextprotocol.io/) **| The "USB-C Port" for Vertical Integration**

The first challenge for an AI agent is interacting with the digital environment around it. The Model Context Protocol (MCP) forms the bedrock for agents to interact with the traditional web and defines how an agent discovers and utilizes external functionalities by acting as the universal **"USB-C port" for AI agents**.

Championed by Anthropic and adopted by major players like Google and Microsoft, MCP replaces the need for custom, fragile integrations. Instead of building a unique connector for every database or API, developers build a standardized MCP interface. If a tool "speaks" MCP, any agent can plug in and instantly understand how to use it.

MCP can be secured by implementing protocols in the agent identity and commerce layers. Without external identity protocols, MCP relies on capability discovery as a proxy for identity. It allows a tool to self-identify its specific functions to the agent. When an agent plugs in, the tool presents its "identity" in the form of exposed resources and prompts, effectively saying, "I am a database with these tables" or "I am a browser tool that can read this page." This allows the agent to instantly understand the tool's ‘identity’ and how to employ it.

[**Agent-to-Agent: Agent2Agent Protocol (A2A)**](http://a2a-protocol.org/) **| The "Yellow Pages" for Horizontal Collaboration**

While MCP connects agents to tools, the true power of the agent economy lies in collaboration. The Agent2Agent Protocol (A2A)—originally developed by Google and now hosted by the Linux Foundation—sets the standard for how autonomous agents find peers, negotiate work, and execute complex tasks together.

Identity in A2A is built directly into discovery via "AgentCards". Think of an AgentCard as a **digital business card** or a " **LinkedIn Profile** " for an agent. Hosted publicly by the agent, it declares exactly who the agent is ("I am a Travel Agent"), who built it ("Verified by ABC Company"), and what skills it offers ("I can book flights and check visas"). This essentially creates a " **Yellow Pages** " for the agent economy. It allows a general purpose "Personal Assistant" agent to search for, verify, and "hire" a specialized "Travel Agent" to complete a specific task.

Crucially, A2A goes beyond simple chat between agents. It standardizes their Task Lifecycle, allowing one agent to assign a specific job to another, track its progress in real-time, and receive the final work product.

1. #### The Trust Gap: The Broken Handoff from Human to Machine

While MCP and A2A effectively solve the discovery of tools and peers (identifying *what* a tool or agent is), they do not inherently solve **verifiable identity** (proving *who* is acting and *who* authorized them).

To address verifiable identity for agents, we must first look at the "handoff"—the critical moment when a human user attempts to empower an autonomous agent to execute the task they just discovered. Currently, this handoff relies on a fragile interplay between two distinct standards:

- For Humans (OAuth Authorization Code Flow - [**RFC 6479**](https://datatracker.ietf.org/doc/html/rfc6749#)): This is the gold standard for user login. A human acts interactively (e.g., "Log in with Google"), proving their identity to a trusted provider.
- For Machines (Identity Assertion Grant - [**RFC 7521**](https://datatracker.ietf.org/doc/html/rfc7521) and [**RFC 7523**](https://datatracker.ietf.org/doc/draft-ietf-oauth-identity-assertion-authz-grant/)): Once the human steps away, the software must act on its own. The industry relies on this "incumbent" standard, which acts as a "notarized letter" allowing a server to assert its identity to another system.

The "Trust Gap" occurs during the handoff between these two protocols. When a human uses the Authorization Code Flow, they are present and consenting. But when they hand a task to an autonomous agent, that agent must switch to the Identity Assertion Grant to execute the work. Current infrastructure is struggling with three critical complexities when handling this handoff:

- **Impersonation vs. Delegation:** The current standard is binary. It either identifies the machine (the server) or fully impersonates the user (using the user's credentials to log in as them). It lacks the sophisticated middle ground required for agents: "I am Agent X, acting on behalf of User Y (validated via Auth Code Flow), but only with specific permissions". It cannot distinguish between "Alice logging in" and "Alice's assistant booking a flight".
- **Identity vs. Intent:** The Authorization Code Flow proves who is there, but the subsequent Assertion Grant fails to capture what they wanted. The standard answers "Who is there?" but not "What are they allowed to do right now?". In the agent economy, we need verifiable intent—a merchant needs to know not just that the agent belongs to Alice, but that Alice specifically authorized the purchase of this flight at this price.
- **Static vs. Dynamic:** The incumbent model assumes infrastructure is static and long-lived (like a permanent "Service Account"). It breaks down with AI agents, which are dynamic and ephemeral. These mobile agents need a portable identity they can carry with them, not a permanent account wired into a backend server.
1. #### The New Solution: Protocols Addressing Agent-Specific Identity

The industry is responding to the 'Trust Gap' with new protocols designed explicitly for autonomous actors. These standards address agent-specific identity, moving beyond simple authentication to provide the infrastructure for granular delegation, cross-cloud portability, and decentralized trust.

[**MCP-Identity (MCP-I)**](https://modelcontextprotocol-identity.io/) **| The Company ID Badge and Signed Permission Slip**

MCP-Identity (MCP-I) is designed to secure the vertical "agent-to-tool" interaction. It acts as the " **company ID badge + signed permission slip** " for tool access, answering the critical security question: "Which human user gave this specific agent permission to do this?".

It leverages W3C Verifiable Credentials (VCs) and Decentralized Identifiers (DIDs) to deliver three critical security layers:

- **Granular Delegation ("The Permission Slip"):** It attaches cryptographically verifiable proof of user delegation. This answers "Who authorized this?" and enables granular control—for example, authorizing an agent to "read" a calendar but not "delete" events.
- **Verified Identity Attributes ("The ID Badge"):** The VCs can also carry verified attributes about the agent itself. This answers "Who is this agent?" by proving critical details like vendor identity ("Built by ABC Company") or compliance status ("SOC2 Certified").
- **Edge Enforcement:** MCP-I assigns every agent a unique Agent DID that is independent of the tool it is calling. This prevents "service account" sprawl. Because the Agent DID acts as the anchor, requests can be verified at the network edge (e.g., proxies) without hitting the application server. This filters unauthorized traffic before it reaches the database, providing a critical shield for the agent economy.

[**AGNTCY**](https://agntcy.org/) **| The "Complete Stack" and “Digital Passport” for Interoperability**

While MCP handles the tool layer and A2A handles the peer layer, AGNTCY—launched by Outshift, a Cisco Company, and stewarded by the Linux Foundation—provides the overarching infrastructure stack that makes them work across any vendor or cloud. It serves as the "connective tissue" of the agent economy.

AGNTCY leverages the Open Agent Schema Framework (OASF) to create a universal standard for how agents describe their capabilities. Whether an agent is built on Google's stack or an open-source framework, OASF ensures it can be discovered and understood by others. It utilizes Secure Low-latency Interactive Messaging (SLIM) to handle the actual data transport. This ensures that when agents talk, the connection is multi-modal, high-speed, and secure—effectively acting as the "fiber optic cables" of the agent internet.

Legacy protocols assume identity is tied to a permanent, static server IP. At its core, AGNTCY solves this by providing the universal " **Digital Passport** ". Built on open standards like W3C Decentralized Identifiers (DIDs) and Verifiable Credentials (VCs), it attaches a persistent, verifiable identity to the agent itself—not the server it runs on and ensures it travels with it across platforms. This ensures that the "handoff" of authority is preserved. An agent can prove it is the same authorized entity whether it is operating on a local device, inside a corporate cloud, or traversing the open web, effectively carrying its reputation and permissions with it.

### The Commerce Layer: A Spectrum of Trust

To build a complete agent economy, we must acknowledge that commerce operates on a sliding scale of trust. The frictionless anonymity required for a fraction-of-a-cent API call is fundamentally at odds with the rigorous identity proofing needed for high-value corporate procurement. The current landscape is responding by correctly solidifying the endpoints of this spectrum, establishing specialized, divergent infrastructure for the market's two extremes.

#### 1\. The Lightweight Micropayment Rail

Payment-only protocols like [**X402**](https://www.x402.org/) (Coinbase’s implementation) and [**H402**](https://h402.xyz/) (the generic community standard) are pioneering the "payment-for-access" model. By leveraging the HTTP 402 "Payment Required" status code, they strip commerce down to its barest essentials: speed and anonymity.

X402/H402 works like the " **Vending Machine** " for the agent economy. The process is stateless and instant: an agent requests a resource and, instead of a login prompt, receives an HTTP 402 invoice (a “challenge”). The agent pays this invoice—typically with crypto/stablecoins—and immediately gains access. This model is ideal for high-volume, low-value interactions where trust is minimal or simply not required, like paying a few cents for a single API call or data query.

However, the "Vending Machine" has a hard ceiling. Because the act of payment is the access, the model is anonymous by design. It offers no mechanism for managing a stateful customer relationship. You cannot run a subscription business, save user preferences, or manage a recurring billing cycle through a vending machine. This is where the simple payment-for-access model reaches its limit.

#### 2\. The High-Assurance Transaction Framework

On the opposite end of the spectrum lies the infrastructure for high-stakes commerce. Frameworks like the Agent Payments Protocol (AP2) and Agent Commerce Kit (ACK) are building the " **B2B Purchase Order** " for the agent economy.

These systems prioritize auditability over speed. They utilize verifiable credentials and rigorous authorization flows to create a formal, cryptographic "paper trail". This infrastructure is essential for high-value, high-risk, or heavily regulated transactions—where proving exactly what a user authorized is more important than how fast the transaction clears.

[**Agent Payments Protocol (AP2)**](https://ap2-protocol.org/) **| The "Digital Contract" for High-Value Commerce**

Launched by Google, the Agent Payments Protocol (AP2) is an open protocol designed to make agent commerce safe, auditable, and dispute-proof. It works across all payment methods, from Visa and PayPal to crypto.

AP2 is built on a role-based architecture that strictly separates concerns by assigning different roles to players in an ecosystem. For example, it distinguishes between the "User Agent" (who finds the product) and the "Credentials Provider" (who secures the pay credentials), ensuring that the entity browsing the web never has direct access to the user's private keys.

In the physical world, high-value business deals require a contract, not just a handshake. AP2 brings this rigor to the agent economy by using **“Verifiable Digital Credentials (VDCs).”** Instead of just sending a payment request, the agent exchanges these cryptographically secured credentials, known in AP2 as "Mandates":

- **The Cart Mandate:** Used when the user is present. It is generated by the Merchant and signed by the user. It binds the user’s identity to the exact details of a cart, creating a non-repudiable record of the deal.
- **The User-Signed Intent Mandate:** Used when the user isn't watching. Generated by the Shopping Agent, it’s a pre-signed instruction (e.g., "buy these tickets if they drop below $100"), giving the agent secure, bounded authority to act in the background.
- **The Payment Mandate:** A signal sent to the bank proving an AI was involved, allowing issuers to assess risk without blocking the transaction as fraud.

These "Mandates" are built as VDCs; they create a permanent, tamper-proof record. AP2 acts as a security wrapper around existing payment systems, connecting with identity providers to prove who signed the credential. This ensures that every transaction has an unforgettable paper trail.

[**Agent Commerce Kit (ACK)**](https://www.agentcommercekit.com/) **| The "Business-in-a-Box" for Autonomous Agents**

While AP2 is a contract, the Agent Commerce Kit (ACK) is the entire office. It is a comprehensive, open-source framework that gives an agent everything it needs to start a business: a verified identity, a wallet, and a receipt printer.

Most developers don't want to build a commerce system from scratch. ACK provides a modular, "turnkey" solution with two core components:

- **ACK-ID (The Digital Badge):** A built-in identity layer leveraging the W3C Verifiable Credentials and Decentralized Identifiers standards. It assigns every agent a globally unique identifier and issues credentials that answer the question, *"Can I trust this AI?"* By linking the agent to a verifiable human or company owner, it ensures that when an agent sells a service, you know exactly who is responsible for it.
- **ACK-Pay (The Cash Register):** A universal payment terminal. It allows agents to accept payments (crypto or traditional) and, crucially, issue **Verifiable Receipts**. This means every transaction comes with a digital "proof of purchase" that can be audited later.

ACK is designed to be the "Shopify for Agents"—a self-contained ecosystem that works out of the box. However, it doesn't lock you in. A developer can use ACK's payment system while using AGNTCY for identity, or use ACK's identity system to pay via X402. It is the flexible foundation for agents that need to buy, sell, and trade autonomously.

#### 3\. The Relational Rail for Everyday Commerce

To build a fully functioning agent economy, we cannot rely solely on anonymous micropayments or complex corporate procurement. A complete ecosystem requires a third, central pillar: a Relational Rail designed for everyday commerce.

This middle ground represents the backbone of the modern digital economy—the world of B2C e-commerce and Software-as-a-Service (SaaS). Unlike the "Vending Machine" model of X402 (optimized for stateless speed) or the "Purchase Order" model of AP2 (optimized for auditability), this layer requires a protocol that creates and maintains stateful relationships, which handles the standard interaction models that drive the modern web:

- **Account Creation:** Signing up for a service and establishing a verified identity.
- **Subscription Management:** Managing the recurring $10/month for a SaaS tool or API plan.
- **High-Value Consumer Purchases:** Booking a flight or buying shoes, where the merchant must know who the customer is.
- **Relationship Management:** Earning loyalty points, saving order history, or managing user preferences.

KYAPay is the purpose-built protocol for this relational layer, capable of handling both the first transaction (account creation) and all subsequent transactions (relationship management). It is designed not to replace the other rails, but to complement them. By offering the speed of a lightweight system with the trust of an identity-linked one, it bridges the stack, allowing agents to move seamlessly from anonymous browsing (via X402) to becoming trusted, long-term customers.

Building on the philosophy of **pragmatic trust**, KYAPay offers a **"Secure Checkout"** experience that manages the entire lifecycle of a commercial relationship, from acquisition to retention.

To ensure ease of adoption, KYAPay leverages **JSON Web Tokens (JWTs**)—the same standard already used by millions of developers for web authentication. It utilizes three token primitives to handle specific commercial interactions:

- `**kya**` **(Know Your Agent) Token:** The "Sign-Up" Flow. An agent presents this token to definitively identify itself and create an account with a merchant.
- `**pay**` **Token:** The "Recurring" Flow. An agent that is already known (logged in) presents this token to authorize a specific payment, ideal for subscription renewals or repeat purchases.
- `**kya-pay**` **Token:** The "Secure Guest Checkout". This combined token allows an agent to simultaneously identify itself, create an account, and authorize the initial payment in a single, atomic step.

While KYAPay is optimized for speed, it shares the same architectural DNA as the high-assurance layers, ensuring seamless interoperability:

- **Shared Trust Anchors:** Just as AP2 relies on a " **Credentials Provider** " (Identity Provider) to act as the trust layer between buyer and seller, KYAPay utilizes a " **Token Issuer**." Both roles serve the identical function of anchoring trust—validating an agent's legitimacy before a sale.
- **Complementing ACK:** KYAPay is designed to work *within* the **Agent Commerce Kit (ACK)** ecosystem. It can serve as the lightweight "Guest Checkout" module for fast onboarding, while allowing merchants to upgrade users to full ACK-ID verification for higher-value transactions later.

By providing this flexible, identity-linked option, KYAPay harmonizes the commerce stack. It gives merchants the verified identity they need for long-term relationships without the heavy infrastructure of a corporate contracting system, ensuring that every agent has the right tool for the right transaction.

### The Cooperative Stack

The "Internet of Agents" will not be defined by a single monolithic platform, but by a vibrant, fast-evolving **Cooperative Stack**. Just as the modern web relies on the seamless interplay of HTTP for pages, SMTP for email, and TLS for security, the agent economy thrives on specialized protocols working in concert.

In this unified architecture, every layer plays a distinct yet interconnected role:

- **MCP** creates the " **USB-C Port** " for universal tool access.
- **A2A** generates the " **Yellow Pages** " for peer discovery.
- **AGNTCY** issues the " **Digital Passport** " for portable identity.
- **X402** powers the " **Vending Machine** " for instant micropayments.
- **AP2 & ACK** enforce the " **B2B Purchase Order** " for high-stakes assurance.

**KYAPay** anchors the center of this ecosystem as the " **Secure Checkout** ". It harmonizes the stack, providing the **Relational Rail** that allows agents to navigate between anonymous interactions and high-assurance contracts. By enabling agents to become trusted, long-term customers, KYAPay unlocks the full potential of everyday autonomous commerce.