---
title: "Summary: Agent Discovery Problem (MindStudio, 2026)"
type: summary
topic: personal-project
source_type: company-blog
tags: [discovery, trust, mcp, agent-app-store, capability-manifests, federation]
sources: [mindstudio-discovery-problem.md]
created: 2026-04-22
updated: 2026-04-22
---

# Summary: Agent Discovery Problem (MindStudio, 2026)

**Author:** MindStudio Team

**Source:** `mindstudio-discovery-problem.md` | MindStudio blog, 2026-04-10

**Answers:** *How does MindStudio frame the agent discovery problem for a practitioner audience?*

---

## Key framing

Clearest practitioner articulation of the three-layer discovery problem:

1. **Existence discovery** — does an agent that can do X exist?
2. **Capability discovery** — what exactly can it do; what inputs/outputs?
3. **Trust and quality discovery** — is it reliable and safe to invoke?

**What exists today:** Hardcoded orchestration, shared tool registries (LangChain, CrewAI), MCP (solves standardized invocation but not trust/quality), proprietary agent-to-agent APIs.

**MCP framing:** "It's more like a power outlet standard than a full app store." MCP is necessary infrastructure, not a complete solution.

**What an agent-native app store needs:** Structured capability manifests, semantic search, quality/reliability signals, trust/provenance verification, versioning, invocation standards.

**Federated vs. centralized:** Likely hybrid — public registries for general-purpose agents, private organizational registries for internal agents, cross-registry queries when authorized.

**Organizational challenge is as important as technical.** No owner for the catalog; agents built ad hoc; governance missing before an agent can be discoverable.

---

## Relevance to thesis

This source directly informed the [[discovery-problem]] concept page. MindStudio's framing of "app store" as the right metaphor for what's missing positions the startup similarly — as the trust and quality infrastructure that MCP doesn't provide. MindStudio is positioning themselves as part of the solution; the startup provides the layer above (verification, evaluation, cross-org accountability) that MindStudio's infrastructure doesn't address.

## Source

- [[mindstudio-discovery-problem]] (MindStudio Team, 2026-04-10)
