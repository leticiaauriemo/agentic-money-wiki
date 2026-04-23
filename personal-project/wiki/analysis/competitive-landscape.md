---
title: "Competitive Landscape"
type: analysis
topic: personal-project
tags: [competition, positioning, strategy]
sources: []
created: 2026-04-22
updated: 2026-04-22
---

# Competitive Landscape

## The stack layers

| Layer | What it does | Examples | Our relationship |
|---|---|---|---|
| Foundation models | Core reasoning | OpenAI, Anthropic, Google | Customer of |
| Agent frameworks | Building agents | LangGraph, CrewAI, Strands | Build on top of |
| Memory infrastructure | Agent memory | [[mem0]], [[letta]], Zep | Partner / use |
| Agent clouds | Run-your-own agents | [[aws-agentcore]], Vertex AI, Azure Foundry | Coexist (different buyer) |
| Agent builders | No-code agent tools | [[mindstudio]], Relevance AI | Not competitors (dev tool) |
| Discovery directories | Find agents | MCP Registry, A2A, llm-agents.info | Above / use |
| Payment rails | Agent-to-agent payments | [[x402]], [[mpp]], Stripe | Settle through |
| **Enterprise trust layer** | **Vetted subcontracting service** | **[us — empty position]** | **This is us** |

## Key competitors in detail

See individual company pages:
- [[aws-agentcore]]
- [[mindstudio]]
- [[mem0]]
- [[letta]]
- [[coinbase-agentic-market]]
- [[stripe-mpp]]

## The pitch against each

**vs AWS AgentCore:** AWS sells infrastructure for a company running its
own agents. We sell a managed service for a company hiring agents from
others. Different product, different buyer. AgentCore is a walled-garden
orchestration engine; we are cross-org interoperability.

**vs MindStudio:** They are a publishing and tooling platform — build your
agent, expose it as an MCP server, done. We run the marketplace that uses
those listings with verification and trust layered on top. We could list
MindStudio-hosted agents as specialists.

**vs Mem0/Letta:** They solve per-agent memory for one organization's
agents. We solve per-client context across a curated specialist network
that spans multiple organizations. Orthogonal problems.

**vs Coinbase Agentic.market:** They are building the public payment and
discovery layer (x402, open registries). We are the enterprise trust and
service-delivery layer that sits on top of what they built. Complementary
positioning, not directly competitive.

**vs hyperscalers in general:** They build walled gardens optimized for
keeping workloads inside their cloud. We build cross-platform
interoperability optimized for matching the right specialist to the job
regardless of where it runs.

## The empty chair

The "enterprise trust layer" row of the stack is genuinely empty today.
Nobody is doing vetted, managed, cross-org agent subcontracting with
per-client context accumulation. This is the bet.

## Open questions on competition

See [[open-questions]] — "Competitive" section.
