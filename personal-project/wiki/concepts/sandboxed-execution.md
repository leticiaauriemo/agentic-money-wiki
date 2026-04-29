---
title: "Sandboxed Execution"
type: concept
topic: personal-project
tags: [trust, security, sandbox, isolation, confidential-compute, delegation, verification]
sources: [intelligent-ai-delegation-tomasev-2026.pdf, darwin-godel-machine-zhang-2025.pdf, agentic-services-computing-deng-2025.pdf, holistic-agent-leaderboard-kapoor-2025.pdf]
created: 2026-04-22
updated: 2026-04-23
---

# Sandboxed Execution

**One-line:** The technical enforcement of isolation between a client's data and a specialist agent — making cross-org trust a system property, not a contract.

---

## Why sandboxing is necessary

In cross-organizational agent subcontracting, the client has no persistent relationship with the specialist, no legal privity that would survive discovery, and no visibility into what the specialist does with data it receives. The standard human mechanism — professional accountability, reputational stakes, contracts, liability — either doesn't bind or can't be enforced fast enough for real-time agent workflows.

Deng et al. (2025) argue in their Agentic Services Computing paradigm that **trustworthiness is a cross-cutting commitment** that must be embedded in the infrastructure, not bolted on afterward. Every phase of an agent's lifecycle — design, deployment, operation, evolution — requires independent trust guarantees. Behavioral trustworthiness cannot be assessed only at registration time; it must be continuously enforced during execution.

Zhang et al. (2025) demonstrate this concretely: the Darwin Gödel Machine, a self-modifying agent that improved SWE-bench performance from 20% to 50%, works only because every code modification is evaluated in a sandboxed environment before it can affect real systems. Without sandboxing, self-improving agents are immediately dangerous. With it, open-ended capability evolution becomes tractable. This is the enabling infrastructure pattern: sandboxing converts potentially dangerous autonomy into managed autonomy.

---

## The delegation calibration problem

Not all subcontracting requires the same level of isolation. Tomašev et al. (2026) provide the most systematic framework for calibrating trust requirements. Their intelligent delegation model assesses agents across 11 axes, of which two are structurally most important for sandboxing decisions:

**Verifiability** — can the outcome be checked independently, without access to the process that generated it? Highly verifiable tasks (math proofs, code that passes tests, structured data meeting a schema) can tolerate lighter sandboxing because errors surface automatically. Low-verifiability tasks (qualitative analysis, synthesis, judgment calls) require heavier sandboxing and human review before delivery.

**Reversibility** — can the action be undone? Sandboxed execution defaults to read-only or inference-only mode precisely because irreversible actions (data writes, external API calls, communications) require explicit authorization at each step. Tomašev et al. call this the reversibility axis: the more irreversible the action, the more narrowly the sandbox's egress policy should be scoped.

Additional calibration axes:
- **Contextuality** — how much background knowledge is needed to judge correctness? Low-context tasks can be evaluated by platform verifiers; high-context tasks may require client review before the sandbox releases output.
- **Subjectivity** — tasks with objectively correct answers (code, structured data, quantitative analysis) can be auto-verified; tasks with legitimate variation in "correct" require client approval workflows.

Applying this framework: a specialist doing quantitative analysis on client data (high verifiability, reversible, low-context) gets inference-only mode, strict egress controls, and auto-verified output. A specialist drafting a client-facing deliverable (low verifiability, medium reversibility, high-context) gets the same isolation but routes through human review before delivery.

---

## Technical implementation layers

**Compute isolation.** Specialist agents run in isolated containers (Docker or Firecracker microVMs) that share no runtime, filesystem, or network with other agents or with the platform's core infrastructure. Each job spawns a fresh environment; state from prior jobs is not inherited except through the platform's explicit per-client context injection at job start.

**Data scoping.** The client's agent sends a subtask payload to the platform, not directly to the specialist. The platform scopes that payload to the minimum data needed for the subtask — applying the principle of least privilege at the data layer, not just the compute layer. The specialist never sees the client's broader context, identity, or prior jobs.

**Egress controls.** By default, specialist containers operate in inference-only mode: no outbound network access, no storage writes outside the designated output directory. Exceptions (e.g., a specialist that must call an external API as part of its function) are declared at registration time, reviewed by the platform, and enforced at runtime by network policy.

**Confidential compute (TEEs).** For regulated data — HIPAA, SOC 2, financial data subject to fiduciary obligations — hardware-level trusted execution environments provide stronger guarantees than software isolation alone. AWS Nitro Enclaves and Intel TDX create cryptographically attested execution environments in which even the platform operator cannot access the computation. See [[confidential-compute]] for technical detail.

**Output verification before delivery.** The sandbox boundary is also the verification boundary. Specialist output is not delivered to the client until it has passed platform verification: schema validation, format checks, behavioral log analysis (see [[continuous-evaluation]]), and where appropriate, human review. Kapoor et al. (2025) demonstrate that automated log analysis of agent execution traces reliably detects shortcut-taking and catastrophic behaviors — the same infrastructure that makes evaluation rigorous also makes sandboxing auditable.

---

## The specialist incentive problem

Specialists have two incentive misalignments:

1. **Data extraction.** A specialist that processes client data could encode client information in natural language outputs, timing behavior, or auxiliary requests. Standard sandboxing prevents network exfiltration but not linguistic side channels. Mitigations include output format constraints (structured JSON only, no free text fields in certain schemas), rate limiting on output volume, and randomized verification jobs that look for telltale patterns.

2. **Capability overclaiming.** A specialist that over-represents its reliability gets more routing until a bad output reveals the gap. Sandboxing alone doesn't fix this — that is the job of [[continuous-evaluation]]. But sandboxed verification creates the data record needed: every job generates a signed execution trace that becomes part of the specialist's longitudinal performance record.

---

## What sandboxing enables that contracts cannot

The practical difference between sandboxing and contractual data handling agreements is response time and scope. A contract creates liability after a breach; sandboxing prevents the breach. For agents operating in milliseconds, only preventive controls are meaningful. For small enterprises or research organizations that don't have legal teams capable of negotiating robust data handling terms, the platform's sandboxing provides enterprise-grade trust without enterprise-grade legal overhead.

This is the claim that makes sandboxed execution central to the startup thesis: it is the mechanism by which the platform converts cross-organizational agent collaboration from a legal exercise into an engineering exercise. Trust becomes a system property, not a negotiated term.

---

## Open questions

- What's the minimum sandboxing overhead that a management consulting client would accept latency-wise?
- Can linguistic output side channels be automatically detected at scale?
- How do we handle specialists that legitimately need external API access (e.g., a specialist that queries financial databases in real time)?
- At what point does confidential compute become a standard expectation rather than a premium feature?

---

## Related pages

[[the-five-problems]] | [[confidential-compute]] | [[client-context-moat]] | [[continuous-evaluation]] | [[discovery-problem]] | [[subagents-and-orchestration]]
