---
title: "Overview — Startup Thesis"
type: overview
topic: personal-project
tags: [thesis, product, strategy]
sources: []
created: 2026-04-22
updated: 2026-04-22
---

# Overview — Startup Thesis

## The problem (two walls)

Enterprise AI agents hit two walls that existing infrastructure doesn't solve:

**The memory wall.** Agents excel at bounded tasks and break at long
jobs. Context overflows, original instructions get diluted, errors from
one step cascade into the next, state is lost on any interruption, and
nobody notices the output is wrong until much later.

**The discovery problem.** The fix for the memory wall is to decompose
jobs across multiple specialist agents. But discovering, evaluating, and
trusting specialist agents — especially from outside your own
organization — has no good solution today. Everything is hand-wired.

Together, these two walls prevent enterprises from safely subcontracting
agent work across organizational boundaries.

## The product

A managed service where enterprise-client agents send complex jobs to
be decomposed, routed to vetted specialists running in a sandboxed
environment, verified before delivery, with accumulated per-client
context making every subsequent job better than the last.

**Not software. Service.** Clients buy outcomes, not toolkits.

## The five layers

1. Orchestration that handles the memory wall by design
2. Discovery and routing that solves the cross-organizational matching
3. Vetted specialist network with continuously measured performance
4. Sandboxed execution that enforces trust technically, not contractually
5. Per-client context memory that compounds with every job

## The wedge

Financial services research first. Then legal. Then compliance. Verticals
where data sensitivity makes the safety story a feature, buyers have
budget, and outputs are judgment-heavy enough that clients pay for quality.

## The moat

Per-client context accumulated over years of real work. A new entrant with
a better model starts at zero with each client. This platform starts every
job already knowing the client.

## Key cross-references

See [[the-five-problems]] for the detailed problem breakdown.
See [[competitive-landscape]] for how this differs from MindStudio, AWS
AgentCore, Mem0, Coinbase Agentic.market, and others.
See [[open-questions]] for the strategic questions still being worked out.
