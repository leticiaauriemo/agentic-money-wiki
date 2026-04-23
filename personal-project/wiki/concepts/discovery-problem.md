---
title: "Discovery Problem"
type: concept
topic: personal-project
tags: [discovery, registry, trust, multi-agent, capability, internet-of-agents]
sources: [mindstudio-discovery-problem.md, ioa-agent-discovery-guo-2025.pdf, internet-of-agents-chen-2024.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Discovery Problem

**One-line:** The three-layer unsolved problem of how one AI agent finds, evaluates, and trusts another — especially across organizational boundaries. MCP solves communication. It does not solve trust or quality at scale.

## Why this problem exists

In human organizations, discovery is easy. You ask a colleague, search a directory, check LinkedIn. You find who you need, confirm they can help, and get to work.

Agents don't have this. As agent deployments scale — enterprise teams building dozens of internal agents, third-party specialists emerging across the ecosystem — the inability to discover and coordinate creates bottlenecks that cancel out the efficiency AI was supposed to deliver. Every multi-agent connection today is hand-wired. A developer explicitly configures which agents talk to which, what their capabilities are, and how to call them.

This works for small closed systems. It does not scale. And it entirely prevents cross-organizational agent collaboration — which is where the most valuable interactions will happen.

## Three layers of discovery

Discovery is not one problem. It is three distinct problems that each require different solutions.

### Layer 1: Existence
Does an agent that can do X exist somewhere I can reach?

Current state: partially solved within frameworks (LangChain, CrewAI tool registries), not solved across organizations. MCP servers are discoverable by MCP-compatible clients — but only if you already know where the server is. There is no global index.

### Layer 2: Capability
What exactly can it do? What inputs does it expect? What outputs does it produce? What are its limitations and failure modes?

Current state: MCP capability manifests describe individual function signatures. They do not describe agent-level reliability profiles, appropriate use cases, or the nuances a calling agent needs to decide whether to trust this agent with a specific job. The gap between "can take this input" and "is the right agent for this task" is not captured by any current protocol.

Agents are also not static services. Unlike traditional APIs with versioned, predictable behavior, agents reason and improvise. Two calls with identical inputs may return different results. Capability descriptions that work for tools break down for agents with flexible reasoning.

### Layer 3: Trust and quality
Is this agent reliable? Does it produce accurate outputs? Is it safe to invoke on sensitive data?

Current state: essentially unsolved. No production system provides verified quality signals, trust scores, or cross-organizational accountability for specialist agents. This is the layer where market failure is most acute.

## What exists today

**Hardcoded orchestration.** The most common pattern — a developer writes an orchestrator that explicitly lists every sub-agent it can call. Works for closed systems; doesn't scale; breaks every time an agent changes.

**Shared tool registries.** LangChain, CrewAI, and similar frameworks provide registries for tools and agents. Framework-local — no cross-org or cross-framework discovery.

**Model Context Protocol (MCP).** Anthropic's open standard for standardized capability description and invocation. The most significant recent development. MCP solves: "how do I call this?" and partially "what can it do?" MCP does not solve: trust verification, quality signals, or cross-organizational accountability. It is the power outlet standard. It is not the app store.

**Agent2Agent (A2A).** Google's protocol for agent-to-agent communication. Complementary to MCP — handles coordination and delegation between agents. Explicitly defers authorization logic to implementation-specific policies. Does not solve the trust or quality layers.

## The IoA framework (Guo et al., 2025)

Guo, Wang, Su et al. (Xi'an Jiaotong University, 2025) frame this as the "Internet of Agents" (IoA) — a paradigm where billions of autonomous agents interact and collaborate at scale. Their key insight: agent capability is **inherently heterogeneous and context-dependent**, which makes standard search and matching approaches insufficient.

They propose a two-stage capability discovery framework:

1. **Autonomous capability announcement** — agents credibly publish machine-interpretable descriptions of their abilities. The emphasis on "credibly" is important: the announcement system must be designed so that false or inflated capability claims are costly or detectable.

2. **Task-driven capability discovery** — context-aware search, ranking, and composition to locate and assemble suitable agents for specific tasks. Not keyword search — semantic matching that understands the specific requirements of a job.

Their framework integrates semantic capability modeling, scalable updatable indexing, and memory-enhanced continual discovery. The "memory-enhanced" component is significant: past interactions with a specialist improve future matching — which is the discovery layer of the per-client context moat.

## Why trust is the hardest layer

Even if existence and capability are solved, cross-organizational trust remains structurally hard for three reasons specific to agents (explored more in [[econ136-proposal]]):

**Zero-cost misrepresentation.** A human professional who overclaims capability suffers reputationally in their network. An agent has no social embedding — it can claim any capability at zero marginal cost. The informal mechanism that disciplines human professional markets doesn't apply.

**Non-persistent identity.** Human reputation systems work because identity is persistent — bad behavior follows you. An agent can be instantiated fresh with no history. Without technical enforcement of identity, reputation cannot attach to an agent.

**Dynamic capability.** A model update can change an agent's performance between evaluation and execution. Quality signals go stale in a way that human professional credentials don't.

## What a full solution would look like

A complete discovery system needs:
- **Structured capability manifests** — machine-readable, beyond function signatures to reliability profiles, edge cases, data handling policies
- **Semantic search** — matching a task description to suitable agents, not keyword lookup
- **Verified quality signals** — continuous benchmarking by the platform, not self-reported claims
- **Trust and provenance** — who built this agent, what data does it access, what are its security properties
- **Versioning** — which model version was evaluated, deprecation notices when behavior changes
- **Invocation standards** — MCP or A2A as the execution layer once discovery returns a match

The organizational challenge is as hard as the technical one. Even with perfect protocols, enterprises need to own their agent catalog, assign governance, and take responsibility for agents they deploy. Most don't have this process yet.

## Connection to the startup thesis

The platform's core function is solving Layer 3 for a curated specialist network. Existence (Layer 1) and capability (Layer 2) are partially addressed by MCP registries. Trust and quality (Layer 3) — specifically in the cross-organizational context — is where the platform adds value that no protocol alone can provide.

The discovery system also seeds the [[client-context-moat]]: the platform learns which specialists work for which clients, improving routing over time in ways that a new entrant starting from scratch cannot replicate.

## Related pages

[[the-five-problems]]
[[memory-wall]]
[[subagents-and-orchestration]]
[[mcp]]
[[a2a]]
[[continuous-evaluation]]
[[client-context-moat]]
[[econ136-proposal]]

## Sources

- [[mindstudio-discovery-problem]] (MindStudio blog, 2026-04-10)
- [[ioa-agent-discovery-guo-2025]] (Guo et al., Xi'an Jiaotong University, 2025)
- [[internet-of-agents-chen-2024]] (Chen et al., Tsinghua/Peking University, 2024)
