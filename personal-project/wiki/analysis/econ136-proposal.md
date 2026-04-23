---
title: "Econ 136 Project Proposal"
type: analysis
topic: personal-project
tags: [class, proposal, market-design, matching, disclosure, reputation]
created: 2026-04-22
updated: 2026-04-22
---

# Econ 136 Project Proposal
**Stanford Economics 136 — Market Design**
**Instructor: Paul Milgrom**
**Due: May 1, 2026**

---

## Topic

**When Markets Can't Form: Institutional Design for AI Agent Marketplaces**

This paper studies why markets for specialist AI agents currently fail to form at scale — and what market design can fix it. The argument is not about pricing or auction format. It is about the absence of the informal social infrastructure that makes human professional services markets work, and what formal mechanisms must substitute when that infrastructure does not exist.

---

## The Problem

AI agents are beginning to subcontract work to one another. Enterprise clients deploy agents to perform complex tasks — research, compliance monitoring, due diligence — and increasingly need to route subtasks to specialist agents outside their own organizations. Emerging infrastructure (Anthropic's Model Context Protocol, Google's Agent2Agent protocol, Coinbase's Agentic.market) provides the communication layer. What it does not provide is the trust layer.

The result is that today's multi-agent systems are almost entirely hand-wired: every agent-to-agent connection is established manually by a developer who knows both parties. This is not a technical limitation. It is a market design failure — the same failure that kept medical residency matching bilateral and unstable before the NRMP, and that kept kidney exchange impossible before Roth's clearinghouse. The agent market has not formed because the institutional infrastructure for trust does not exist.

What makes this problem specific to agents — and not just a standard information asymmetry — are three properties that distinguish agent markets from human professional services markets:

**1. Zero-cost misrepresentation.** A human consultant who overclaims capability suffers reputationally across their career and professional network. The social cost is real and persistent. An agent has no social embedding. It can claim any capability at zero marginal cost, with no informal penalty. The mechanism that disciplines human markets is simply absent.

**2. Non-persistent identity.** Human markets rely on identity persistence for reputation to accumulate and be meaningful. An agent can be instantiated fresh, with no history, at any time. Without technical enforcement of identity, reputation cannot attach to an agent in the way it attaches to a person or firm.

**3. Dynamic capability.** A model update can fundamentally change an agent's performance overnight — between when it was evaluated and when it executes a job. Human professional skills change slowly. An agent's capability is not a stable type. Contracts and evaluations become stale in ways that have no parallel in human labor markets.

Together, these three properties mean that the informal mechanisms sustaining human professional services markets — social reputation, persistent identity, stable capability — are all absent simultaneously. The question is what formal mechanisms can substitute.

---

## Research Questions

1. Why do agent markets currently fail to form beyond bilateral hand-wired connections? Can the logic of market unraveling (Roth and Peranson, 1999) be applied to explain the fragmentation of agent markets?

2. Milgrom's (1981) unraveling-of-disclosure result holds when private information is verifiable and competition is present. How do zero-cost misrepresentation and non-persistent identity break each condition, preventing voluntary disclosure from arising?

3. What formal mechanisms can substitute for the missing social infrastructure?
   - Platform-run evaluation: synthetic benchmarks as a verification technology
   - Identity commitment: cryptographic identity as a substitute for social persistence
   - Capability versioning: treating agent capability as a contract term that must be pinned to a specific model version (connecting to Milgrom and Hatfield's Matching with Contracts)

4. When does a stable, efficient market exist under these mechanisms — and when does it still unravel?

---

## Theoretical Framework

**Market unraveling (Class 4).** I will apply the logic of Roth and Peranson's analysis of the medical residency market to agent markets. The NRMP unraveling story: without a centralized clearinghouse enforcing a common timeline and stable matching, bilateral deals form early, markets fragment, and efficiency is lost. Agent markets exhibit the same pathology — but driven by trust failure rather than timing. I will characterize the conditions under which a clearinghouse (the platform) can restore stability.

**Truthful mechanisms and incentive compatibility (Classes 3 and 10).** The core mechanism design question: given zero-cost misrepresentation, under what conditions is truthful capability reporting a dominant strategy? I will model this as a mechanism design problem where the platform chooses evaluation and payoff rules to induce truthful reporting, analogous to the incentive-compatible mechanisms studied in the context of the deferred acceptance algorithm.

**Matching with contracts (Class 15).** Milgrom and Hatfield (2005) extend matching theory to settings where the terms of the match — not just the identity of the match — are part of the equilibrium. Agent capability is not fixed at matching time; it depends on which model version is deployed. Capability versioning — pinning an agent's contract to a specific evaluated version — is a direct application of this framework. I will ask whether stable matchings with capability-versioned contracts exist and when they are efficient.

---

## Key References

**Course-connected:**
- Roth, A. and Peranson, E. (1999). "The Redesign of the Matching Market for American Physicians." *American Economic Review*.
- Hatfield, J. and Milgrom, P. (2005). "Matching with Contracts." *American Economic Review*.
- Milgrom, P. (1981). "Good News and Bad News: Representation Theorems and Applications." *Bell Journal of Economics*.
- Akerlof, G. (1970). "The Market for Lemons." *Quarterly Journal of Economics*.

**Agent markets (empirical grounding):**
- Bansal, G. et al. (2025). "Magentic Marketplace: An Open-Source Environment for Studying Agentic Markets." Microsoft Research. *(7,680 simulated procurement scenarios; 34.6% failure rate absent governance — empirical evidence of market failure.)*
- Rothschild, D. et al. (2025). "The Agentic Economy." Microsoft Research.
- Guo, S. et al. (2025). "Agent Discovery in Internet of Agents: Challenges and Solutions."
- Shapira, N. et al. (2026). "Agents of Chaos." *(Red-team evidence of governance failures in live autonomous agent systems.)*
- Liu, J.H. (2026). "Building an AI Agent-Oriented Market: Institutional Design, Protocol Economics, and Governance for Machine-Native Trade."

---

## What I Expect to Argue

**The agent market fails to form for the same structural reason that pre-NRMP medical matching failed** — there is no trusted clearinghouse and no mechanism enforcing stability. But the cause is different: not timing pressure, but the absence of the social infrastructure that makes informal trust possible between humans.

**Zero-cost misrepresentation, non-persistent identity, and dynamic capability each independently break the conditions that make human professional markets work.** Together they make a self-sustaining agent marketplace impossible without formal institutional design.

**Three mechanisms are jointly necessary — none is sufficient alone:**
- Platform evaluation (synthetic benchmarks) restores verifiability, enabling the Milgrom unraveling result to hold
- Identity commitment (cryptographic persistence) restores the reputational attachment that makes long-run incentives work
- Capability versioning in contracts (connecting to Matching with Contracts) handles dynamic capability by making the evaluated version a contract term

**A clearinghouse that implements all three can achieve stable, efficient matching.** I will characterize this equilibrium and the conditions under which it breaks down — particularly the bootstrap problem: the clearinghouse needs evaluation data to route, but needs routing volume to generate evaluation data.

---

## Data and Empirical Grounding

The paper is primarily theoretical. I will use Bansal et al.'s (2025) Magentic Marketplace simulation — 7,680 procurement scenarios with varying governance conditions — as the empirical anchor. Their result that market failure rates drop sharply when verification and governance infrastructure are present directly supports the theoretical claim that institutional design, not pricing, is the binding constraint.

---

## Notes

*[Your edits and additions below this line]*
