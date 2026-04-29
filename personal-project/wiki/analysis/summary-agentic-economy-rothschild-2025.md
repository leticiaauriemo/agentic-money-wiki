---
title: "Summary: The Agentic Economy (Rothschild et al., 2025)"
type: summary
topic: personal-project
source_type: academic
tags: [agentic-economy, market-structure, discovery, trust, walled-garden, communication-friction, two-sided-markets]
sources: [agentic-economy-rothschild-2025.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Summary: The Agentic Economy (Rothschild et al., 2025)

**Authors:** David M. Rothschild, Markus Mobius, Jake M. Hofman, Eleanor Dillon, Daniel G. Goldstein, Nicole Immorlica, Sonia Jaffe, Brendan Lucier, Aleksandrs Slivkins, Matthew Vogel (Microsoft Research)

**Source:** `agentic-economy-rothschild-2025.pdf` | arXiv:2505.15799

**Answers:** *What is the economic framing for why agent-to-agent interaction matters?*

---

## Core argument

The paper's central claim is that the more profound economic impact of generative AI is **not** individual productivity gains — those are already underway — but rather the reduction of **communication frictions between consumers and businesses**. This friction reduction could reorganize markets, redistribute power, and catalyze new products and services.

The key distinction the authors draw:

- **Unscripted interaction** — agents can communicate flexibly in natural language, not just via rigid web forms. *Enabled by technical advances (NLP, MCP, A2A).*
- **Unrestricted interaction** — agents can interact with any other agent, not just those within a closed platform. *Depends on market structure and governance — not solved by technology alone.*

Current agents achieve unscripted; the unrestricted question is open.

---

## Current state of agents (two types)

**Siloed service agents** (Amazon Rufus, Expedia Romie): provide natural language interfaces within a single company. Do not expose interfaces for agent-to-agent interaction. Still require a human to navigate to them.

**End-to-end agents** (OpenAI, Google, Microsoft): general-purpose, can navigate external websites — but currently via "computer use" models that simulate a human pointing and clicking. There is no true service agent on the business side. This limits capability to what businesses currently expose through existing web forms.

The limitation is structural, not just a capability gap: businesses built for human interfaces don't have the agentic APIs needed for agent-to-agent commerce.

---

## The walled garden vs. web of agents question

The architecture question the paper frames as central:

**Agentic walled gardens:** A few dominant platforms (Apple, Google, Microsoft, Meta, OpenAI, Anthropic) control which agents interact. Similar to today's app stores. Benefits: quality baseline, fraud filtering, discoverability, insurance on agent mistakes. Risks: concentrated power, fragmented ecosystems, profit extraction.

**Web of agents:** Fully open, decentralized — any agent can transact with any other. Like the World Wide Web. Requires: large-scale coordination on standards and protocols across corporations and governments, plus "robust mechanisms for discovery, trust, and security among interacting agents."

> **Key quote (Conclusion):** "The architecture of agentic communication will determine the extent to which generative AI democratizes access to economic opportunity."

---

## The role of two-sided platforms

Today's intermediaries (Amazon, Expedia, Spotify) create value by standardizing both sides of a transaction. An agentic economy could eliminate the need for them — assistant agents could negotiate directly with service agents.

However, intermediaries may still create value through: trusted discovery, validation, remediation (dispute resolution, insurance), and economies of scale. The paper expects **fierce competition** between intermediaries due to low switching costs, compressing their profit margins even if they survive.

---

## Advertising and the preference economy

In today's internet, attention is the scarce resource. In an agentic economy, attention is less constrained — what matters is the **algorithm matching assistants to service agents**.

The paper predicts a shift from the "attention economy" to a **"preference economy"**: high-quality human feedback on goods and services becomes the scarce and valuable resource. Success depends on attracting early engaged users who provide feedback, creating a flywheel.

---

## Micro-transactions and unbundling

With agents handling friction, micro-transactions become economically viable — previously too inconvenient to handle manually.

Unbundling and rebundling: agents can deconstruct digital goods (a news article, a software subscription, a bundle of services) and reconstruct personalized versions, enabling usage-based micro-payments instead of fixed subscriptions.

---

## Key quotes

> "We argue that the more profound economic impact lies in reducing communication frictions between consumers and businesses. This shift could reorganize markets, redistribute power, and catalyze the creation of new products and services." (Abstract)

> "A web of agents requires large-scale coordination among many players—including corporations and governments—to develop and agree upon standards and protocols. It also requires robust mechanisms for discovery, trust, and security among interacting agents." (Section 3.2)

> "The truly scarce and valuable resource—particularly, in a web of agents—will be high-quality human feedback on goods and services." (Section 3.3)

---

## Relevance to thesis

1. **Foundational framing.** The paper names exactly the gap the startup addresses: the open web of agents requires "discovery, trust, and security" mechanisms that do not yet exist. The startup provides those mechanisms in the enterprise B2B context.

2. **Walled garden risk.** Rothschild et al. explicitly frame the walled garden scenario as a risk — concentrated platform power limiting who benefits. A neutral enterprise trust layer with an open specialist network represents the "web of agents" architecture applied to enterprise workflows.

3. **Two-sided platform insight.** Even in an agentic economy, platforms that provide verified discovery, remediation, and quality guarantees retain value. This is the moat articulation: not just routing, but trust, verification, and accountability that pure protocol standards can't provide.

4. **Preference economy.** "High-quality human feedback" as the scarce resource maps directly to the [[continuous-evaluation]] flywheel — the platform accumulates outcome signals that improve routing and become a proprietary quality signal.

---

## Related pages

[[overview]]
[[discovery-problem]]
[[the-five-problems]]
[[competitive-landscape]]
[[continuous-evaluation]]
[[client-context-moat]]

## Source

- [[agentic-economy-rothschild-2025]] (Rothschild et al., Microsoft Research, 2025)
