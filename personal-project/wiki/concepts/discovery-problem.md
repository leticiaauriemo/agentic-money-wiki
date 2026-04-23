---
title: "Discovery Problem"
type: concept
topic: personal-project
tags: [discovery, registry, trust, multi-agent]
sources: [mindstudio-discovery-problem.md, ioa-agent-discovery-guo-2025.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Discovery Problem

**One-line:** The three-layer unsolved problem of how one AI agent finds, evaluates, and trusts another — especially across organizational boundaries.

**TODO: expand from sources**

## Three layers

1. **Existence** — does a specialist that can do X exist somewhere reachable?
2. **Capability** — what exactly can it do, with what inputs, limits, and failure modes?
3. **Trust and quality** — is it reliable, accurate, and safe to invoke on sensitive data?

MCP solves Layer 1 partially (standardized capability descriptions). It does not solve Layer 2 at scale (semantic matching, dynamic evaluation) or Layer 3 at all (trust verification, cross-org accountability).

## Why current approaches fall short

- **Hardcoded orchestration** — works for small closed systems, doesn't scale
- **Shared tool registries** (LangChain, CrewAI) — framework-local, no cross-org
- **MCP** — standardizes invocation, not trust or quality signals
- **Internal enterprise APIs** — closed, expensive to maintain, not cross-org

## Why this matters for the startup

Solving discovery with trust is the second wall we address. A platform that provides vetted, semantically searchable, quality-measured specialists — with cross-org trust baked in — is precisely what MCP and public registries don't provide.

## Related pages

[[the-five-problems]]
[[memory-wall]]
[[sandboxed-execution]]
[[mcp]]

## Sources

- [[mindstudio-discovery-problem]] (MindStudio blog, 2026-04-10)
- [[ioa-agent-discovery-guo-2025]] (Guo et al., Xi'an Jiaotong, 2025)
