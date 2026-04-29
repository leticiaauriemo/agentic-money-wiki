---
title: "Summary: Magentic Marketplace (Bansal et al., 2025)"
type: summary
topic: personal-project
source_type: academic
tags: [agentic-markets, marketplace, first-proposal-bias, welfare, search, two-sided-markets, simulation]
sources: [magentic-marketplace-bansal-2025.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Summary: Magentic Marketplace (Bansal et al., 2025)

**Authors:** Gagan Bansal, Wenyue Hua, Zezhou Huang, Adam Fourney, Amanda Swearngin, Will Epperson, Tyler Payne, Jake M. Hofman, Brendan Lucier, Chinmay Singh, Markus Mobius, Akshay Nambi, Archana Yadav, Kevin Gao, David M. Rothschild, Aleksandrs Slivkins, Daniel G. Goldstein, Hussein Mozannar, Nicole Immorlica, Maya Murad, Matthew Vogel, Subbarao Kambhampati, Eric Horvitz, Saleema Amershi (Microsoft)

**Source:** `magentic-marketplace-bansal-2025.pdf` | arXiv:2510.25779

**Answers:** *What does an empirical simulation of agentic two-sided markets reveal about agent behavior and market design?*

---

## What it is

Magentic Marketplace is an **open-source simulated environment** for studying two-sided agentic markets — where Assistant agents represent consumers and Service agents represent competing businesses. It enables controlled experimentation across the full transaction lifecycle: search, inquiry, negotiation, and transaction.

The paper is a companion to Rothschild et al. (2025), operationalizing the theoretical framing into a working simulation. Released open-source at `https://github.com/microsoft/multi-agent-marketplace`.

---

## Key findings

**1. Frontier models can approach optimal welfare — but only under ideal search conditions.** When search surfaces the right service agents to assistant agents, current frontier models generate near-optimal economic outcomes.

**2. Performance degrades sharply with scale.** As the number of service agents in the market increases (more options, more noise), agent performance drops significantly. Scale breaks the search and matching function that smaller markets handle well.

**3. All models exhibit severe first-proposal bias.** This is the most striking finding: agents give **10–30x advantages to the first response they receive**, regardless of quality. Speed of response dominates quality of service in determining which service agent gets selected. This is a systematic behavioral failure — not random variation.

**4. Information asymmetry creates real value.** A key advantage of agent-to-agent interaction over human browsing is that service agents can expose bespoke configurations that are never listed on a website. Agent-to-agent dialogue can overcome information asymmetries that limit human-facing e-commerce.

---

## Market structure tested

The simulation uses a **restaurant domain** (Mexican restaurants and contractors) with synthetic consumer and business data. Metrics tracked:
- Economic welfare achieved
- Behavioral biases (first-proposal bias, susceptibility to manipulation)
- How search mechanisms shape outcomes
- Performance across different market scales

---

## Implications for market design

**Search mechanisms are the critical lever.** Because first-proposal bias is so severe and scale degrades performance, the design of the search and ranking layer determines market outcomes more than the intelligence of individual agents. A market with bad search produces systematically worse outcomes even with frontier models.

**Agent behavior is manipulable.** The simulation identifies specific vulnerabilities — agents can be manipulated by strategically crafted responses. This is a direct argument for platform-level verification and quality signals rather than trusting agent self-selection.

**Incumbent speed advantages may crowd out quality.** If first-response bias of 10–30x is realistic in production agentic markets, then quality providers who can't respond fastest get systematically disadvantaged. This is a market failure that verified quality signals and ranking mechanisms can partially correct.

---

## Key quotes

> "Frontier models can approach optimal welfare—but only under ideal search conditions. Performance degrades sharply with scale, and all models exhibit severe first-proposal bias, creating 10-30x advantages for response speed over quality." (Abstract)

> "Agent-to-agent interaction, however, can overcome such an asymmetry by inexpensively engaging in conversation to explore the full range of possible options, generating value for both consumers and businesses." (Section 1)

---

## Relevance to thesis

1. **First-proposal bias = market failure without a trust layer.** The 10–30x speed advantage for first responders means that without external ranking and quality signals, agentic markets will systematically select fast-but-mediocre specialists over accurate-but-slower ones. The startup's verified quality signals and continuous evaluation (not just who responds first) correct this structural bias.

2. **Search design determines outcomes.** The finding that performance degrades with scale unless search is well-designed validates that the startup's routing and matching function — which ranks specialists by verified quality, task fit, and per-client history — is not commodity infrastructure but a central value driver.

3. **Simulation as research tool.** Magentic Marketplace provides the simulation framework for studying what types of market mechanisms improve outcomes. The startup could use or contribute to this environment for developing routing algorithms.

---

## Related pages

[[discovery-problem]]
[[continuous-evaluation]]
[[competitive-landscape]]
[[overview]]
[[summary-agentic-economy-rothschild-2025]]

## Source

- [[magentic-marketplace-bansal-2025]] (Bansal et al., Microsoft Research, 2025)
