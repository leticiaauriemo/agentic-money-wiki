---
title: "Model Context Protocol (MCP)"
type: rail
topic: personal-project
tags: [mcp, protocol, discovery, interoperability]
sources: [mindstudio-discovery-problem.md]
created: 2026-04-22
updated: 2026-04-22
---

# Model Context Protocol (MCP)

**Type:** open protocol
**One-line:** Anthropic's open standard for AI models to connect to external tools and data sources through a standardized interface — the leading protocol for capability description and invocation.

**TODO: expand**

## How it works

MCP defines how an AI model (client) discovers and calls an external tool or agent (server). Servers publish structured capability manifests; clients query and invoke them through a standard interface. Any MCP-compatible system can call any MCP server without custom integration.

## Agent-friendliness

High for discovery and invocation. MCP solves "how do I call this?" and partially "what can it do?" It does not solve trust verification, quality signals, or cross-org accountability — which is our layer.

## Who is building on it

Anthropic, MindStudio, Cursor, LangChain. Significant ecosystem momentum.

## Our relationship

MCP is infrastructure we build on top of. Specialists in our network can be exposed as MCP servers. Clients access our platform via MCP. We add the trust, vetting, routing, and context layers above the raw protocol.

## Sources

- [[mindstudio-discovery-problem]]
