---
title: "Summary: Agentic Services Computing (Deng et al., 2025)"
type: summary
topic: personal-project
source_type: academic
tags: [agentic-services, lifecycle, governance, multi-agent, trustworthiness, orchestration, ASC]
sources: [agentic-services-computing-deng-2025.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Summary: Agentic Services Computing (Deng et al., 2025)

**Authors:** Shuiguang Deng, Hailiang Zhao, Ziqi Wang, Guanjie Cheng, Peng Chen, Wenzhuo Qian, Zhiwei Ling, Jianwei Yin, Albert Y. Zomaya, Schahram Dustdar (Zhejiang University, University of Sydney, TU Wien)

**Source:** `agentic-services-computing-deng-2025.pdf` | arXiv:2509.24380

**Answers:** *What is the full lifecycle and governance model for agentic services?*

---

## Core contribution

Proposes **Agentic Services Computing (ASC)** as a new paradigm — the convergence of classical multi-agent systems (MAS), services computing, and LLM-based agents. In ASC, services are:
- **Not invoked but orchestrated**
- **Not reactive but proactive**
- **Not static but evolving participants in dynamic ecosystems**

The paradigm is organized around a **four-phase lifecycle**: Design → Deployment → Operation → Evolution.

---

## Four research dimensions

The paper organizes the field around four interwoven dimensions:

1. **Perception and context modeling** — agents must interpret multimodal environments and maintain long-term context
2. **Autonomous decision-making** — planning, tool use, self-improvement (VOYAGER, ReAct, REACT loop)
3. **Multi-agent collaboration** — team formation, task delegation, coordination protocols
4. **Evaluation with alignment and trustworthiness** — the dimension that is currently most underdeveloped

The critical observation: these dimensions are **not isolated layers**. They co-evolve. Contextual grounding supports deployment; autonomous reasoning drives action; collaboration emerges from interaction; trustworthiness must be maintained as a lifelong cross-cutting commitment.

---

## Why classical approaches failed

**Classical MAS (JADE, Jason, SPADE):** Rich theoretical models of autonomy and coordination but constrained by hand-crafted knowledge bases and rigid planning mechanisms. No adaptability in open environments.

**Traditional services computing:** Robust principles for distributed system design but treats services as passive, stateless components without cognitive capabilities.

**LLM-based agents alone:** Remarkable reasoning and adaptability but lack mechanisms for auditability, value alignment, safety, and long-term operational rigor.

ASC addresses these gaps by **unifying** the three domains rather than combining them additively.

---

## On governance and trustworthiness

The paper identifies trustworthiness as a "lifelong, cross-cutting commitment across all lifecycle stages." This is not a bolt-on at the end — it must be embedded in design, deployment, operation, and evolution.

Key tension: as agents become increasingly autonomous, they introduce new challenges in governance, safety, and trust. The interaction model has shifted from "static protocol-driven exchanges" to "dynamic cognition-driven engagements that continuously evolve." Existing paradigms are inadequate.

---

## Key quotes

> "A service is no longer a fixed function awaiting invocation; it is a proactive entity capable of perception, reasoning, action, and collaboration." (Section I)

> "ASC reorients the focus of service design: from service invocation to agent orchestration, from predefined workflows to emergent collaboration, and from functional correctness to behavioral trustworthiness." (Section I)

---

## Relevance to thesis

1. **"Behavioral trustworthiness" is the product.** The startup's core value proposition aligns exactly with what ASC identifies as the underdeveloped dimension: evaluation, alignment, and trustworthiness across the full agent service lifecycle. The paper provides academic framing for why this is hard and necessary.

2. **Lifecycle framing for the platform.** ASC's four phases (Design → Deployment → Operation → Evolution) map to the startup's service: the platform manages specialists through their full lifecycle — onboarding, routing, monitoring, re-evaluation, retirement.

3. **The convergence of three traditions.** ASC synthesizes MAS (structure), services computing (lifecycle management), and LLMs (capability) — which is exactly the conceptual space the startup occupies. The startup is an ASC instantiation focused on the enterprise trust layer.

---

## Related pages

[[subagents-and-orchestration]]
[[sandboxed-execution]]
[[continuous-evaluation]]
[[the-five-problems]]

## Source

- [[agentic-services-computing-deng-2025]] (Deng, Zhao et al., Zhejiang University/University of Sydney/TU Wien, 2025)
