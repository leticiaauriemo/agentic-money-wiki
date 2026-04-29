---
title: "Summary: Internet of Agents (Chen et al., 2024)"
type: summary
topic: personal-project
source_type: academic
tags: [multi-agent, heterogeneous-agents, distributed, orchestration, team-formation, internet-analogy]
sources: [internet-of-agents-chen-2024.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Summary: Internet of Agents (Chen et al., 2024)

**Authors:** Weize Chen, Ziming You, Ran Li, Yitong Guan, Chen Qian, Chenyang Zhao, Cheng Yang, Ruobing Xie, Zhiyuan Liu, Maosong Sun (Tsinghua University, Peking University, BUPT, Tencent)

**Source:** `internet-of-agents-chen-2024.pdf` | arXiv:2407.07061

**Answers:** *What does a working multi-agent framework for integrating heterogeneous third-party agents look like?*

---

## Core contribution

IoA is a **framework for multi-agent collaboration** inspired by the Internet. It addresses three fundamental failures of existing multi-agent systems:

1. **Ecosystem isolation** — most frameworks only use agents defined within their own ecosystem; third-party agents can't integrate
2. **Single-device simulation** — existing systems can't distribute agents across multiple physical devices
3. **Rigid communication** — hard-coded pipelines can't adapt to dynamic task requirements

IoA treats agent collaboration like the Internet: any agent can join, discover others, and form teams dynamically.

---

## Architecture

**Server** (central hub):
- Agent registry for registration and discovery
- Message routing between agents and group chats
- Session management for connections

**Client** (wrapper for individual agents):
- Adapts any agent to IoA's protocol
- Provides agent contact and communication functionality

**Three layers for both:** Interaction layer → Data layer → Foundation layer

---

## Key mechanisms

**Agent integration protocol.** Enables different third-party agents running on different devices to integrate into the framework. Includes a standard agent message format that any compliant agent can produce and consume.

**Instant-messaging-like architecture.** Agents communicate through group chats — dynamic teams form around tasks, similar to how people spin up a Slack channel for a project. The analogy is deliberate: the goal is ad-hoc collaboration, not rigid workflows.

**Dynamic team formation.** When an agent receives a task, it queries the agent registry for agents that match capability requirements. It can autonomously form a team, invite agents, and start collaborating within a group chat context.

**Conversation flow control.** Using finite-state machine mechanics inspired by Speech Act Theory, agents can autonomously determine the state of a conversation — discussion, task assignment, execution — and transition between states.

---

## Experimental results

IoA was tested by integrating AutoGPT and Open Interpreter as agents:
- **66–76% win rate** in open-domain task evaluations vs. AutoGPT or Open Interpreter individually
- Outperforms GAIA benchmark (general assistant tasks) with only a few basic ReAct agents
- In RAG question-answering: GPT-3.5-based IoA implementation achieves performance close to or exceeding GPT-4 alone
- Surpasses previous multi-agent frameworks across all tested domains

---

## Key quotes

> "The Internet has revolutionized the way people collaborate and share knowledge... This global network has enabled the creation of remarkable collaborative projects, such as Wikipedia and the development of the Linux operating system, which would have been impossible for any single person to achieve." (Introduction)

> "By autonomously searching for potential agents capable of handling the tasks at hand, agents can dynamically decide to form different teams and communicate within various group chats." (Section 2.1)

---

## Relevance to thesis

1. **The Internet analogy is the cleanest framing.** Chen et al.'s Internet-of-Agents framing gives the startup a natural narrative: the startup is building the infrastructure that makes the "Web of Agents" (Rothschild's term) a reality for enterprise workflows.

2. **Dynamic team formation is the right decomposition model.** Rather than hard-coded orchestration (where the orchestrator knows about every possible specialist in advance), IoA's discovery-then-team approach is what the startup's routing layer should approximate — but with trust verification and quality signals layered on top.

3. **Third-party agent integration is the gap IoA solves technically; trust is the gap the startup solves institutionally.** IoA shows that technical integration of heterogeneous agents is possible. The startup's contribution is making those integrations trustworthy across organizational boundaries.

---

## Related pages

[[discovery-problem]]
[[subagents-and-orchestration]]
[[mcp]]
[[a2a]]

## Source

- [[internet-of-agents-chen-2024]] (Chen, You, Li, Guan et al., Tsinghua/Peking University, 2024)
