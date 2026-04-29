---
title: "Continuous Evaluation"
type: concept
topic: personal-project
tags: [evaluation, routing, reputation, quality-flywheel, benchmarks, staked-reputation, HAL]
sources: [holistic-agent-leaderboard-kapoor-2025.pdf, magentic-marketplace-bansal-2025.pdf, meta-agent-inefficiencies-el-stanford-2025.pdf, agentic-services-computing-deng-2025.pdf, ioa-agent-discovery-guo-2025.pdf]
created: 2026-04-22
updated: 2026-04-23
---

# Continuous Evaluation

**One-line:** The system by which specialist agents compete on measured performance — synthetic benchmarks plus anonymized real jobs — feeding routing decisions and creating a quality flywheel.

---

## Why continuous evaluation is non-negotiable

The central market failure in agent markets is what Milgrom (1981) calls **unraveling**: when quality is unobservable at purchase time, high-quality providers are systematically underselected, eventually exiting the market and leaving only low-quality providers. For human professional services, informal mechanisms — reputation, credentials, professional associations, persistent client relationships — serve as quality signals that prevent full unraveling. For agents, none of these mechanisms transfer: identity is non-persistent, credentials are unverifiable at runtime, and reputation systems for AI agents don't exist.

Static capability manifests — the agent equivalent of a resume — make this worse, not better. A specialist can claim any capability at registration time with zero cost. Without continuous empirical measurement, the platform cannot distinguish a genuine specialist from a general-purpose model making specific claims.

Continuous evaluation is the platform mechanism that substitutes for these missing social structures: empirical quality measurement over time, with routing consequences that create incentives for honest performance representation.

---

## The evaluation infrastructure gap

Kapoor et al. (2025), building the Holistic Agent Leaderboard (HAL), document the gap between what current evaluation infrastructure produces and what trustworthy agent evaluation requires. Across 21,730 agent rollouts spanning 9 benchmarks, 9 foundation models, and multiple scaffolding configurations, their key findings are:

**Scaffolds matter as much as models.** The same foundation model produces dramatically different performance depending on how it is scaffolded — memory management, planning structure, tool use patterns, prompt engineering. A platform that evaluates models without controlling scaffold configuration produces misleading quality signals.

**Automated log analysis catches what aggregate scores miss.** Kapoor et al. develop automated analysis of agent execution logs that identifies shortcut-taking behaviors (e.g., hardcoding answers rather than reasoning) and catastrophic behaviors (e.g., deleting test cases to pass evaluation). These behaviors don't show up in benchmark scores but represent fundamental reliability failures. Their system catches these systematically.

**Higher reasoning effort can reduce accuracy.** Counterintuitively, certain scaffold configurations that increase compute and reasoning steps produce *worse* aggregate accuracy. This means standard reasoning benchmarks are insufficient proxies for task quality, and evaluation must attend to the full execution trace, not just the final output.

The implication for the platform: evaluation infrastructure is not a commodity and cannot be purchased off-the-shelf. It is a competitive asset that requires purpose-built investment.

---

## First-proposal bias and the routing problem

Bansal et al. (2025) simulate an open-source agentic marketplace (Magentic Marketplace) and find that **speed, not quality, dominates outcomes** in naive market designs. The first agent to respond with a plausible-sounding answer wins the job — regardless of quality — because clients (or orchestrators) lack mechanisms to hold offers while better responses arrive. Measured across scenarios, this first-proposal bias confers advantages of 10–30x.

This is fatal for specialist quality as a competitive differentiator. If the platform's routing system simply routes to the fastest responder, specialists with genuine deep expertise lose systematically to fast generalists. The platform's routing must:
1. **Hold the auction open long enough** to receive competitive bids from quality specialists
2. **Weight quality signals over response speed** in routing decisions
3. **Use accumulated quality history** to pre-route to likely best performers before the auction starts (reducing the latency cost of quality-weighted routing)

Bansal et al. also find that **frontier models approach optimal social welfare only under ideal search conditions** — where all relevant specialists are discoverable and quality is accurately measured. Their performance degrades sharply as the agent population scales, because search becomes more expensive and quality signals become noisier. The evaluation system is the mechanism that keeps search tractable and signals accurate at scale.

---

## How the evaluation system works

### Layer 1: Synthetic benchmarks

The platform maintains a proprietary set of benchmark tasks across each domain in which specialists operate. Benchmarks have known ground-truth answers and are constructed to resist gaming (no publicly disclosed datasets; new benchmark instances generated on a rolling basis). Specialists are evaluated periodically against current benchmarks, and scores feed routing weights.

Key design requirements:
- **Tasks must match the platform's actual job distribution**, not the research community's preferred benchmarks. General-purpose benchmarks (HumanEval, MMLU) don't predict performance on the specific subtask types the platform decomposes real jobs into.
- **Scaffold must be controlled.** Kapoor et al.'s finding means that specialists must be evaluated on the specific scaffold the platform uses, not their self-reported best configuration.
- **Behavioral logs must be analyzed**, not just outputs. Shortcut detection and catastrophic behavior flags must be part of benchmark evaluation, not just accuracy on final answers.

### Layer 2: Anonymized real jobs

Completed real-client jobs (fully anonymized, with client consent) become additional benchmark instances. A specialist that completed a complex research synthesis for a consulting client — with high client acceptance and no human revision — produces a ground truth instance that future specialists can be evaluated against.

This layer has two effects:
- It ensures benchmark distribution tracks actual client demand rather than synthetic task construction
- It creates a compounding improvement mechanism: as more jobs are completed, the benchmark set grows and the evaluation becomes more discriminating

### Layer 3: Outcome tracking

Beyond in-session output quality, the platform tracks longitudinal outcome signals:
- **Client acceptance rate** — fraction of specialist outputs accepted without human revision
- **Revision depth** — when revision occurs, how extensive was it?
- **Downstream job success** — did subtasks handled by this specialist lead to successful whole-job completion?
- **Human escalation rate** — how often did the platform route to human review because of uncertainty about specialist output?

Guo et al. (2025) identify memory-enhanced continual discovery — maintaining a running history of agent performance across task types and principals — as essential to accurate routing. Outcome tracking implements this: the platform maintains a longitudinal performance model for each specialist across job types, client types, and task complexities.

### Layer 4: Staked reputation

Specialists stake reputation on their benchmark performance. Persistent over-claiming — maintaining high claimed capability scores while delivering poor actual performance — results in routing downweight, reduced volume, and eventual removal from the network.

This mechanism is the complement to sandboxed execution: sandboxing prevents data extraction and unauthorized actions; staked reputation prevents capability misrepresentation. Together, they address the two main specialist incentive problems.

El, Yuksekgonul, and Zou (2025) find that **automated meta-agent generation produces low behavioral diversity** — the specialist population converges on similar solution patterns. The implication is that staked reputation must attend not just to per-specialist quality but to **network diversity**: routing systems should maintain coverage across meaningfully different problem-solving approaches, not just maximize average quality. A network of 50 high-quality but behaviorally similar specialists serves clients less well than a network of 30 high-quality specialists with genuine diversity of approach.

---

## The quality flywheel

The flywheel operates across four timescales:

**Job-level (immediate):** Each job generates outcome signals (acceptance, revision, escalation) that update specialist routing weights and client context profiles in near-real time.

**Batch (weekly/monthly):** Synthetic benchmark runs update aggregate specialist quality scores. Anonymized real jobs are incorporated into benchmark pools. Routing weights are recalibrated.

**Longitudinal (quarterly):** Outcome tracking data enables identification of systematic gaps — specialist domains or task types where quality is consistently insufficient. This drives specialist recruitment and network expansion.

**Architectural (ongoing):** As the evaluation dataset grows, the benchmark construction process becomes more discriminating. Early benchmarks measure broad capability; later benchmarks test finer-grained specialization. Specialist quality thresholds rise as the network matures.

---

## Deng et al. and trustworthiness as a lifecycle commitment

Deng et al. (2025) argue in their Agentic Services Computing framework that trustworthiness cannot be assessed once and assumed to persist — it must be monitored continuously across all four phases of an agent's lifecycle (design, deployment, operation, evolution). A specialist that performs well at registration may degrade as its underlying model is updated, its tooling changes, or its domain knowledge becomes stale.

The continuous evaluation system operationalizes this: it is not a one-time gate at onboarding but a persistent monitoring infrastructure that tracks specialist performance over time. Specialists that were once reliable but have degraded are identified through systematic evaluation — not discovered through a client's bad experience.

---

## Open questions

- **Gaming resistance:** Synthetic benchmarks become stale if their construction logic is discoverable. How do we maintain the adversarial advantage over specialists optimizing specifically for benchmark performance?
- **Evaluation cadence:** Some specialist domains evolve faster than others (e.g., code generation vs. regulatory research). Should benchmark cadence be domain-specific?
- **Transparency:** Should benchmark results be shared with specialists to enable self-improvement, or kept opaque to prevent gaming? Is there a tiered disclosure model that encourages legitimate improvement without enabling gaming?
- **Cross-client portability:** A specialist rated highly by one client type may underperform for another. How should aggregate reputation scores account for client-specific variance?

---

## Related pages

[[the-five-problems]] | [[discovery-problem]] | [[client-context-moat]] | [[sandboxed-execution]] | [[subagents-and-orchestration]] | [[summary-holistic-agent-leaderboard-kapoor-2025]] | [[summary-magentic-marketplace-bansal-2025]]
