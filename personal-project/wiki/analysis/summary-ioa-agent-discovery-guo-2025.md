---
title: "Summary: Agent Discovery in Internet of Agents (Guo et al., 2025)"
type: summary
topic: personal-project
source_type: academic
tags: [discovery, capability-modeling, internet-of-agents, semantic-retrieval, scalability, trust]
sources: [ioa-agent-discovery-guo-2025.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Summary: Agent Discovery in Internet of Agents (Guo et al., 2025)

**Authors:** Shaolong Guo, Yuntao Wang, Zhou Su, Yanghe Pan, Qinnan Hu, Tom H. Luan (Xi'an Jiaotong University)

**Source:** `ioa-agent-discovery-guo-2025.pdf` | arXiv:2511.19113

**Answers:** *What does a technical framework for agent capability discovery look like at IoA scale?*

---

## Core argument

The Internet of Agents (IoA) is a paradigm where billions of autonomous agents interact, coordinate, and collaborate. The central prerequisite is **agent capability discovery**: agents must be able to identify, advertise, and match one another's capabilities dynamically. Current approaches fail because agent capability is **heterogeneous** (structurally diverse across agent types), **autonomous** (self-published and updated), and **context-dependent** (what an agent can do depends on task and current state).

---

## Two-stage discovery framework

**Stage 1: Autonomous capability announcement** — agents credibly publish machine-interpretable profiles describing:
- Built-in skills, tool access, embodied interaction abilities
- Functional and non-functional attributes (latency tolerance, energy constraints, hardware location)
- Credibility is established through standardized benchmarks, sandbox trials, or peer endorsements

**Stage 2: Task-driven capability discovery** — requesting agents formulate intents as semantic queries and perform context-aware search, ranking, and composition:
- Intent understanding: natural language → semantic representation
- Semantic retrieval: multi-criteria ranking (semantic similarity, credibility, real-time availability)
- Task allocation: coordinate and orchestrate workflows from matched agents

---

## Three technical challenges

**Low expressivity in capability modeling.** Static ontologies and hand-crafted templates can't capture heterogeneous agents (LLM agents vs. robots) that continuously generate new capabilities. Need abstraction-to-execution mapping that accommodates dynamic generation and multimodal semantics.

**Limited scalability in retrieval.** Keyword matching fails to capture semantic meaning; dense retrieval is memory-intensive at IoA scale. Need efficient, semantics-aware indexing that handles large-scale high-concurrency conditions.

**Inconsistency in dynamic environments.** Agents frequently join, leave, and update capabilities. Periodic polling produces stale capability information, leading to unsuitable matches. Need real-time responsiveness plus long-term retrieval performance without forgetting.

---

## The proposed scheme (three phases)

**Phase 1: Semantic agent profiling.** Use pre-trained language model (BERT/DistilRoBERTa) to embed structured agent profiles into a unified latent space. Agents with similar functions but different lexical descriptions are positioned nearby. Enables cross-domain discovery.

**Phase 2: Scalable indexing.** Product quantization-inspired approach: compress high-dimensional embeddings into compact discrete codes. Assign agents compact IDs that preserve functional similarity. When new agents join, either map to existing clusters or refine locally without disrupting existing assignments.

**Phase 3: Memory-enhanced continual discovery.** Train retrieval model with memory-preserving mechanism — replay representative historical agents alongside new arrivals to mitigate catastrophic forgetting. Enables accurate, resilient capability discovery over time.

---

## Existing discovery mechanisms surveyed

| Solution | Approach | Gap |
|---|---|---|
| MCP Registry | Publisher submits; GitHub/domain verification | Centralized; no trust signals |
| A2A Agent Cards | Self-hosted JSON at standard URL | Self-published; no verification |
| Microsoft Entra Agent ID | Enterprise identity via Azure | Within-org only; no cross-org |
| NANDA AgentFacts | TTL-based endpoint resolution + capability verification | PoC stage |
| Agent Name Service (ANS) | DNS-inspired + PKI certificate | PoC stage |

---

## Key quotes

> "Agent capability in IoA is inherently heterogeneous and context-dependent, raising challenges in capability representation, scalable discovery, and long-term performance." (Abstract)

> "Capability verification: To establish credibility and foster trust, declared capabilities by agents are validated through standardized benchmarks, sandbox trials, or peer endorsements." (Section IV-B)

---

## Relevance to thesis

1. **Technical substrate for the startup's discovery problem.** The Guo framework is the most rigorous academic treatment of the problem the startup solves at the trust layer. Stage 1 (capability announcement) + Stage 2 (task-driven discovery) maps directly to the platform's routing function.

2. **Verification as the hard layer.** The paper explicitly distinguishes capability *declaration* from capability *verification*. The startup's continuous evaluation infrastructure (synthetic benchmarks, anonymized real jobs) is the verification mechanism that existing protocols don't provide.

3. **Memory-enhanced discovery = per-client context moat.** The "memory-enhanced continual discovery" concept — past interactions improve future matching — is the technical description of how the per-client context advantage compounds.

---

## Related pages

[[discovery-problem]]
[[subagents-and-orchestration]]
[[continuous-evaluation]]
[[client-context-moat]]
[[mcp]]
[[a2a]]

## Source

- [[ioa-agent-discovery-guo-2025]] (Guo, Wang, Su et al., Xi'an Jiaotong University, 2025)
