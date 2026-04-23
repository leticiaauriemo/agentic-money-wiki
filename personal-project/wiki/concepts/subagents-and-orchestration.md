---
title: "Subagents and Orchestration"
type: concept
topic: personal-project
tags: [subagents, orchestration, decomposition, architecture, specialist-agents]
sources: [agent-subagent-skill-tool-piskala-2026.pdf, prime-planning-zou-stanford-2025.pdf, modular-decomposition-multiagent-pan-2025.pdf, mindstudio-memory-wall.md]
created: 2026-04-22
updated: 2026-04-22
---

# Subagents and Orchestration

**One-line:** The architectural pattern of decomposing complex jobs across multiple specialized agents — and the design decisions that determine whether this works or fails.

## The taxonomy: tool, skill, sub-agent, or agent?

Piskala (2026) argues that these terms are used interchangeably in industry discourse, obscuring the most critical design axis: **control over execution**. The right taxonomy is based on control characteristics, not perceived intelligence.

| Construct | Control | Scope | When to use |
|---|---|---|---|
| **Tool** | Fully controlled by caller | Single deterministic function | When behavior must be predictable and auditable |
| **Skill** | Caller controls invocation; skill controls execution steps | Lightweight procedural module | When the procedure is reusable but bounded |
| **Sub-agent** | Delegated control for a subtask; returns result to orchestrator | Bounded task with its own reasoning | When a subtask requires flexible reasoning but must report back |
| **Agent** | Autonomous control over its own goals and methods | End-to-end task ownership | When the system needs to operate independently |

Key principle from Piskala: **autonomy should be earned through necessity, not assumed by default.** Most systems over-architect toward full agents when sub-agents or skills would be more debuggable, more controllable, and cheaper.

## The orchestrator / specialist pattern

The core architecture for solving the [[memory-wall]]:

```
Client agent (orchestrator)
  → receives complex job
  → decomposes into subtasks
  → routes each subtask to a specialist sub-agent
  → collects results
  → synthesizes final output
```

The orchestrator does NOT execute the subtasks itself. It manages state, tracks progress, handles failures, and assembles output. Each specialist runs in its own bounded context — fresh, focused, and unaware of the full job history. This keeps individual agents within reliable context ranges while enabling jobs that would far exceed any single agent's effective context window.

## How subagents get access to data

This is frequently misunderstood. The specialist does not go to the client's computer or environment.

**The correct model — data goes to the specialist, inside a controlled environment:**

```
Client agent
  ↓  packages relevant data for this subtask
  ↓  sends to platform via API

Platform
  ↓  spawns isolated container (only that scoped data inside)
  ↓  routes to specialist

Specialist agent
  ↓  runs inside container
  ↓  cannot reach internet, other jobs, or client's environment
  ↓  produces output

Platform
  ↓  verifies output
  ↓  destroys container
  ↓  returns verified output to client agent
```

**Data scoping.** The client agent packages only what is needed for that specific subtask — not its entire environment. A subtask requiring analysis of three documents receives exactly those three documents. The specialist sees nothing else.

**What the specialist learns.** Specialists run in inference-only mode — they produce outputs, they do not fine-tune on client job data. Model weights do not change. Client documents do not become training data. This is both contractual and technically enforced at the container level.

**Egress control.** The container has egress controls — only the structured output passes through the platform's verification layer. The specialist cannot exfiltrate data through side channels or produce outputs that embed raw client information in encoded form.

**For the most sensitive cases** (regulated financial data, privileged legal documents): confidential compute — the container runs in a hardware-enforced enclave (AWS Nitro Enclaves, Intel TDX) where even the platform cannot see the raw data inside. The client receives cryptographic attestation that only approved code ran on their data. See [[confidential-compute]].

## PRIME: learned orchestration (Stanford, 2025)

Zou, Liu, and Khankari (Stanford, 2025) propose PRIME — Planning with Reflective, Iterative, Multi-agentic Exploration. Key contribution: framing the orchestration problem as **option discovery in reinforcement learning** rather than a hard-coded workflow.

Using Monte Carlo Tree Search (MCTS), PRIME:
1. Decomposes a complex task into subtasks dynamically
2. Selects the optimal reasoning strategy (reflection, debate, voting, etc.) for each subtask
3. Instantiates specialized subagents to execute each subtask

The insight is that the decomposition itself should be learned and optimized — not predetermined by a developer. This makes the orchestrator adaptive to novel job types. PRIME outperforms state-of-the-art on Webshop, PlanBench, and Game of 24, and works well even for small LLMs with limited compute.

**Relevance to the startup:** PRIME suggests that the orchestration layer — decomposing a client job into well-scoped subtasks — is a non-trivial learned capability, not just a routing table. This is a proprietary component of the platform that improves with experience.

## Modular decomposition (Pan et al., 2025)

Pan, Wu et al. (CMU/USC, 2025) propose a multi-agent architecture for modular task decomposition with dynamic collaboration. Key components:

- **Semantic representation layer** — converts natural language task descriptions into unified semantic representations that can be systematically decomposed
- **Modular decomposition mechanism** — breaks the overall goal into hierarchical subtasks
- **Dynamic scheduling and routing** — assigns subtasks to agents and adjusts in real time based on environmental feedback
- **Global consistency mechanism** — ensures coherent connections between subtasks, preventing redundant communication and uneven resource allocation

Their experiments show this architecture outperforms single-agent and static multi-agent approaches in task success rate, decomposition efficiency, and collaboration balance.

## Failure modes in orchestration

Beyond the five individual agent failure modes in [[memory-wall]], orchestrated multi-agent systems have additional failure modes:

**Decomposition errors.** If the orchestrator produces a bad decomposition — wrong subtask boundaries, missing dependencies, wrong specialist routing — every subsequent step compounds the error. Unlike single-agent failures, decomposition errors are hard to detect because each specialist may perform correctly on its assigned subtask.

**State synchronization failures.** When multiple specialists run in parallel, their outputs must be reconciled. Conflicting results, incompatible formats, or missing handoffs between subtasks can corrupt the final synthesis even when individual subtasks succeeded.

**Orchestrator context accumulation.** The orchestrator itself can hit the memory wall if it accumulates all specialist outputs in its own context. Good architecture externalizes orchestrator state to a database — the orchestrator manages job state, not carries it.

**Verification gaps.** If individual specialist outputs are not verified before being passed to the next stage, errors propagate invisibly through the pipeline. Checkpoint verification at each stage is the mitigation.

## The specialist vs. generalist question

A recurring design question: when should a job be sent to a specialist sub-agent vs. handled by a capable general model?

The specialist is worth the routing overhead when:
- It has access to data or tools the general model doesn't have (proprietary databases, real-time feeds, specialized tooling)
- It is fine-tuned or optimized for a specific task type and measurably outperforms the general model on that task
- It provides accountability and auditability that a general model call doesn't (certified outputs, traceable reasoning)

The general model is sufficient when:
- The task is within the general model's reliable capability range
- The overhead of routing, sandboxing, and verification exceeds the quality gain
- The task is one-off and doesn't justify specialist infrastructure

This is the core economic question the platform's routing layer must answer correctly for every subtask.

## Related pages

[[the-five-problems]]
[[memory-wall]]
[[discovery-problem]]
[[sandboxed-execution]]
[[confidential-compute]]
[[continuous-evaluation]]

## Sources

- [[agent-subagent-skill-tool-piskala-2026]] (Piskala, 2026) — taxonomy of tools, skills, subagents, agents
- [[prime-planning-zou-stanford-2025]] (Zou, Liu, Khankari, Stanford 2025) — MCTS-based learned orchestration
- [[modular-decomposition-multiagent-pan-2025]] (Pan, Wu, CMU/USC 2025) — modular decomposition architecture
- [[mindstudio-memory-wall]] (MindStudio, 2026) — multi-agent decomposition as memory wall response
