---
title: "Summary: Agent, Sub-Agent, Skill, or Tool? (Piskala, 2026)"
type: summary
topic: personal-project
source_type: academic
tags: [taxonomy, control, tools, skills, subagents, agents, orchestration, architecture]
sources: [agent-subagent-skill-tool-piskala-2026.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Summary: Agent, Sub-Agent, Skill, or Tool? (Piskala, 2026)

**Author:** Deepak Babu Piskala (Independent Researcher)

**Source:** `agent-subagent-skill-tool-piskala-2026.pdf` | TechRxiv preprint

**Answers:** *What is the principled taxonomy for tools, skills, sub-agents, and agents, and how should practitioners choose?*

---

## The core thesis

The terms "tool," "skill," "sub-agent," and "agent" are used interchangeably in industry discourse, obscuring the most critical design axis: **control over execution**. This creates practical problems: teams over-engineer solutions, adopt unnecessary coordination overhead, and build systems that fail in unexpected ways.

> **Key Insight:** "The key differentiator between tools, sub-agents, and agents is not sophistication or intelligence — it is who controls the execution flow. Control, not intelligence, is the real axis along which agentic systems should be understood."

The right question is not "should this be an agent?" but: **"Who should decide what happens next?"**

---

## The taxonomy

| Construct | Who controls execution | Scope | When to use |
|---|---|---|---|
| **Tool** | Fully controlled by caller | Single deterministic function | Behavior must be predictable and auditable |
| **Skill** | Caller controls invocation; skill controls execution steps | Lightweight procedural module | Procedure is reusable but bounded |
| **Sub-agent** | Delegated control for a subtask; returns result to orchestrator | Bounded task with own reasoning | Subtask requires flexible reasoning but must report back |
| **Agent** | Autonomous control over own goals and methods | End-to-end task ownership | System needs to operate independently |

---

## The "Skills" abstraction (novel contribution)

The paper introduces **Skills** as an underappreciated intermediate construct:
- Lightweight, portable modules of procedural knowledge
- Achieve significant **context efficiency gains through progressive disclosure** — only reveal what the calling system needs at each step
- More powerful than tools (can reason), less autonomous than sub-agents (bounded execution scope)
- Reusable across different orchestrators without modification

Progressive disclosure: the skill exposes its full capability description only when invoked, keeping the orchestrator's context window lean.

---

## Three canonical orchestration patterns

**Tool-centric orchestration:** Main orchestrator calls tools directly. Simple, predictable, easy to debug. Appropriate for well-defined, deterministic operations.

**Hierarchical orchestration:** Orchestrator → sub-agents → tools. Each sub-agent handles a bounded subtask with its own reasoning, reports results up. The pattern the startup's platform uses.

**Decentralized orchestration:** Agents operate as peers with shared memory or communication channels. More autonomous but harder to debug and govern.

---

## The decision framework

The paper concludes with five criteria for choosing the right construct:

1. **How predictable must the behavior be?** More predictable → tool or skill
2. **Who should decide what happens next?** Orchestrator → tool/skill/sub-agent; component → agent
3. **How bounded is the task?** Well-bounded → skill or sub-agent; open-ended → agent
4. **How will you test it?** Tools = unit tests; sub-agents = integration tests; agents = simulation environments
5. **What are the failure modes?** Tool failure is local; agent failure can be systemic

---

## Key quotes

> "Tools can be unit tested. Sub-agents can be integration tested with bounded inputs and outputs. Agents require simulation environments or extensive monitoring because their behavior emerges from an ongoing interaction with their environment." (Section II-B)

> "Autonomy should be earned through necessity, not assumed by default." (Abstract)

> "Gartner predicted that 75% of firms attempting to build 'aspirational agentic architectures' will fail to realize their goals, citing convoluted system designs and unclear governance as primary factors." (Section I-B)

---

## Relevance to thesis

1. **The taxonomy clarifies the platform's value.** The startup's specialists are sub-agents, not agents — they receive a bounded task, reason over it, and return results to the orchestrator. The orchestrator manages job state. This is the right architecture, and Piskala provides the vocabulary to describe why.

2. **"Autonomy earned through necessity."** This principle directly supports the startup's design philosophy: specialists run inference-only on scoped data. They are not granted agent-level autonomy; they are sub-agents with bounded scope. This is a feature, not a limitation.

3. **Progressive disclosure = context efficiency.** The Skills concept maps to the startup's capability manifest design: specialists advertise capabilities progressively, keeping the orchestrator's routing context lean.

---

## Related pages

[[subagents-and-orchestration]]
[[sandboxed-execution]]
[[the-five-problems]]

## Source

- [[agent-subagent-skill-tool-piskala-2026]] (Piskala, Independent Researcher, 2026)
