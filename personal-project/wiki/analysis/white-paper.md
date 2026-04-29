---
title: "The Enterprise Agent Trust Layer: A White Paper"
type: analysis
topic: personal-project
tags: [white-paper, thesis, product, market, architecture]
sources: [agentic-economy-rothschild-2025.pdf, ioa-agent-discovery-guo-2025.pdf, lost-in-the-middle-liu-2023.pdf, mindstudio-memory-wall.md, mindstudio-discovery-problem.md, ai-agent-market-liu-2026.md, magentic-marketplace-bansal-2025.pdf, holistic-agent-leaderboard-kapoor-2025.pdf, intelligent-ai-delegation-tomasev-2026.pdf, internet-of-agents-chen-2024.pdf, prime-planning-zou-stanford-2025.pdf, meta-agent-inefficiencies-el-stanford-2025.pdf, modular-decomposition-multiagent-pan-2025.pdf, agent-subagent-skill-tool-piskala-2026.pdf, agentic-services-computing-deng-2025.pdf, gdpval-openai-2025.pdf, metr-long-task-completion-2025.pdf, darwin-godel-machine-zhang-2025.pdf]
created: 2026-04-23
updated: 2026-04-23
---

# The Enterprise Agent Trust Layer

## Cross-Organizational AI Agent Collaboration and the Market Infrastructure It Requires

---

## Abstract

Autonomous AI agents are approaching expert-level performance on the knowledge work tasks that constitute the productive core of professional services industries. Frontier models are now capable of completing software tasks that take human professionals roughly 110 minutes — and this capability is doubling in scope approximately every seven months (Kwa et al., 2025). Benchmarks covering 44 professional occupations across the top sectors of the U.S. economy show frontier models approaching industry expert quality on deliverable tasks that average seven hours of expert work (Patwardhan et al., 2025).

The implication is not that professional knowledge work will be automated wholesale in the near term. It is that the economic logic of specialization — which distributes production across firms and individuals who each develop comparative advantage in narrow domains — now applies to agents. As Rothschild et al. (2025) argue, the most profound economic impact of AI is not automating individual tasks but reducing the coordination costs that prevent the benefits of specialization from being realized. When agents can reliably find, evaluate, and subcontract to specialist agents, the effective scope of any given agent expands dramatically.

But the infrastructure for cross-organizational agent collaboration does not yet exist. This paper argues that its absence is not a technical gap but a **market design failure**: the informal mechanisms that make human professional services markets work — social reputation, persistent identity, professional certification, legal accountability — are structurally absent in agent markets. Three agent-specific market properties break the standard mechanisms. Five interlocking problems compound them. The result is that today's multi-agent systems are almost entirely hand-wired — every agent-to-agent relationship established manually — which is precisely the bottleneck that AI was supposed to dissolve.

This paper describes the nature of the failure, the architecture of a managed service that addresses it, and the institutional design principles that make such a service durable rather than replaceable.

---

## 1. The Economic Case for Agent Specialization

The economic logic of specialization is ancient. As Becker and Murphy (1992) observe, as technological progress drives greater specialization, it also increases the need for coordination — which in turn demands more sophisticated communication between individuals, organizations, and systems. What AI agents represent, in this frame, is a step-change reduction in the communication friction that has historically capped how far specialization can extend.

Rothschild et al. (2025) make this argument precisely. In *The Agentic Economy*, they distinguish two categories of AI agent impact: the productivity gains from automating individual tasks, which are already underway and well-documented, and the more profound impact of reducing communication frictions between consumers and businesses. The first category improves existing workflows. The second reorganizes markets.

The reorganization logic is Coasean. Ronald Coase's foundational insight was that firms exist because using markets is costly — the friction of finding, evaluating, and contracting with external specialists exceeds the coordination cost of internal management. As Liu (2026) applies this frame to agentic systems: when machines can discover services programmatically, compare structured prices instantly, and route work to specialist providers that are faster and cheaper than self-computation, the market becomes the rational default. Liu's prototype simulation makes the quantitative case: across 7,680 scenarios, successful market routes average \$0.0074 per call and 0.219 seconds of latency, against \$0.300 and 17.5 seconds for self-computation using a general model — yielding mean workflow gains of 90.8x in speed and 40.3x in cost when specialists have genuine comparative advantage.

The important caveat in Liu's analysis is also the central argument of this paper: 34.6% of his scenarios fail entirely — no market trade occurs — because no provider satisfies the active task and policy constraints. A market that reduces exchange friction below the threshold of internal computation must simultaneously embed governance mechanisms sufficient to make delegated action trustworthy. Where either condition fails, markets do not form.

**The walled garden alternative.** Rothschild et al. identify the structural risk: if cross-organizational agent collaboration requires open standards and neutral governance, the temptation of dominant platforms — those with existing large agent user bases — is to create *agentic walled gardens* that restrict which agents can interact. This replicates the app store model at the agent layer, extracting platform rents while limiting innovation and access. The question of whether the emerging agent economy develops as an open web of agents or as a collection of proprietary walled gardens will determine, as Rothschild et al. put it, "the extent to which generative AI democratizes access to economic opportunity." An enterprise trust layer operating as neutral infrastructure between organizational boundaries is the institutional embodiment of the open web scenario.

---

## 2. Two Structural Barriers to Enterprise Agent Collaboration

Before examining why markets fail to form, it is necessary to understand why cross-organizational collaboration is needed at all. The answer lies in two structural limitations of current AI agents — limitations that are not artifacts of early technology but properties of the underlying architecture.

### 2.1 The Memory Wall

AI agents perform reliably within bounded tasks. The empirical record on unbounded, long-running jobs is different. MindStudio (2026) names this the *memory wall* — the structural degradation of agent performance as job complexity and duration increase. It is not a single failure point but a slope of compounding failure modes.

**The empirical foundation.** Liu et al. (2023), in *Lost in the Middle*, provide the landmark empirical basis. Across controlled experiments varying the position of relevant information within long input contexts — using GPT-3.5-Turbo, Claude 1.3, and several open models — they find a consistent U-shaped performance curve: models attend best to information at the beginning and end of context and worst to information buried in the middle. When relevant information is placed in the middle of its input context, GPT-3.5-Turbo's performance on multi-document question answering falls below its *closed-book* performance — meaning the model does better ignoring all documents than trying to use them when the relevant one is buried. Extended-context models specifically designed for long-context tasks show nearly identical curves to standard models: the advertised larger context window does not solve the attention quality problem.

**The five failure modes.** Building on this empirical basis, the practitioner literature identifies five distinct failure modes in long-running agents (MindStudio, 2026):

1. *Context overflow mid-job* — the agent exhausts its token budget and either crashes or silently truncates earlier context, discarding information it needs.

2. *Instruction dilution* — original task instructions, stated clearly at the beginning of context, are progressively pushed toward the middle as tool outputs, intermediate results, and error messages accumulate. The agent drifts from its original goal because its instructions are now in exactly the position where models pay least attention.

3. *Error accumulation* — partial failures cascade. An improvisation around a failed API call becomes context; subsequent steps build on the improvisation; the final output inherits multiple layers of degraded reasoning with no visible seam.

4. *State loss on interruption* — most agent frameworks do not persist execution state. A timeout, rate limit, or server restart destroys the entire context. Restart means re-execution from scratch, often impossible for jobs that have already interacted with external systems.

5. *Evaluation blindness* — the most damaging failure in production: the agent completes the job, the output looks plausible, and nobody identifies the error until it has propagated into a decision. Without systematic verification infrastructure, long-running agents deliver confident-sounding incorrect outputs on a non-trivial fraction of jobs.

**Why scale doesn't fix it.** Larger context windows relieve the immediate pressure of context overflow. They do not address attention quality degradation across long ranges, the state persistence problem, error accumulation dynamics, or evaluation blindness. More significantly, METR (Kwa et al., 2025) demonstrates that frontier model task-completion time horizons — the length of tasks they can complete with 50% reliability — are currently around 110 minutes. This horizon has been doubling approximately every seven months since 2019. The rate may have accelerated since 2024. Even at this extraordinary pace of improvement, the class of jobs that enterprise knowledge workers perform — competitive analyses spanning weeks, regulatory compliance reviews, multi-source research projects — remains well outside the reliable range of any single agent deployment.

**The architectural response.** The correct response to the memory wall is not longer context but decomposition: divide complex jobs into bounded subtasks and assign each to a separate agent with fresh context. An orchestrator manages job state externally while specialist agents handle individual subtasks within reliable ranges. This architectural pattern has independent academic support from multiple directions.

Zou, Liu, and Khankari (Stanford, 2025) demonstrate in PRIME that framing multi-step planning as an *option discovery problem in reinforcement learning* — treating different reasoning strategies as learnable options and using Monte Carlo Tree Search to select among them — produces significant performance improvements over the current state of the art. PRIME outperforms LATS on PlanBench (75% vs. 44%), WebShop (40% vs. 38%), and Game of 24 (36.2% vs. 2.2%), with further improvements when the underlying planner is upgraded. Crucially, PRIME works well for small LLMs with limited compute, suggesting the orchestration advantage compounds independently of raw model capability.

Pan and Wu (CMU/USC, 2025) formalize the modular decomposition approach mathematically: natural language task inputs are converted to semantic embeddings, decomposed into subtask representations via attention-weighted mapping, assigned to specialized agents via dynamic scheduling, and coordinated through a global consistency mechanism that prevents redundant communication and uneven resource allocation. Their experiments show the architecture outperforms both single-agent and static multi-agent approaches on task success rate, decomposition efficiency, and collaboration balance.

Piskala (2026) provides the architectural taxonomy that grounds both approaches: tools, skills, sub-agents, and agents are not equivalent terms but represent distinct positions on a *control axis*. The critical design axis is not sophistication or intelligence but who controls the execution flow. In a properly decomposed system, specialist agents are *sub-agents* — they receive bounded tasks, apply their own reasoning within those boundaries, and return results to an orchestrator. Autonomy is earned through necessity, not assumed by default.

Decomposition is the right architectural response to the memory wall. But it immediately creates the second structural barrier.

### 2.2 The Discovery Problem

Decomposing a job across multiple specialist agents requires that suitable specialists can be found, evaluated, and trusted. This is the discovery problem, and it has three layers that each require different solutions (Guo et al., 2025; MindStudio, 2026):

**Existence.** Does an agent that can perform this specific subtask exist somewhere I can reach? Within a single framework or organization, this is partially solved. Across organizational boundaries, it is not. MCP servers are discoverable by MCP-compatible clients — but only if you already know where the server is. There is no global index of specialist agent capabilities.

**Capability.** What exactly can it do? What inputs does it expect, what outputs does it produce, what are its reliability characteristics and failure modes? Model Context Protocol (MCP) manifests describe individual function signatures. They do not describe agent-level reliability profiles, appropriate use cases, or performance across different input distributions. Agents are not static services — they reason and improvise. Two calls with identical inputs may return different results. Capability descriptions that work for APIs break down for agents with flexible reasoning.

**Trust and quality.** Is this agent reliable? Does it produce accurate outputs on the specific tasks I intend to send it? Is it safe to invoke on data that cannot leave my organization? This layer is essentially unsolved across organizational boundaries. No production system provides verified quality signals, trust scores, or cross-organizational accountability for specialist agents.

Guo et al. (2025) frame this as the central challenge of the Internet of Agents (IoA): "Agent capability in IoA is inherently heterogeneous and context-dependent, raising challenges in capability representation, scalable discovery, and long-term performance." They identify three specific technical challenges. First, *low expressivity in capability modeling* — existing static ontologies and hand-crafted templates are inadequate for heterogeneous agents that continuously generate new capabilities. Second, *limited scalability in retrieval* — keyword matching fails to capture semantic meaning; dense retrieval approaches impose substantial overhead at IoA scale. Third, *inconsistency in dynamic environments* — agents frequently join, leave, and update capabilities; periodic polling produces stale information that leads to unsuitable selections.

Guo et al.'s proposed solution — a two-stage framework combining autonomous capability announcement with task-driven capability discovery using semantic profiling, scalable indexing, and memory-enhanced continual discovery — addresses the technical infrastructure problem. It does not, and explicitly does not, address the trust and quality layer. Verified quality signals for the specific tasks a calling agent intends to send remain outside the scope of any current discovery protocol.

Chen et al. (Tsinghua/Peking, 2024) demonstrate that technical integration of heterogeneous agents across organizational and device boundaries is achievable — their IoA framework achieves 66–76% win rates over individual agents by enabling dynamic team formation around specific tasks. But technical interoperability is necessary, not sufficient, for trustworthy cross-organizational collaboration.

**The current state.** Today's multi-agent systems are almost entirely hand-wired. Every agent-to-agent connection is established manually by a developer who configures capability descriptions, API endpoints, and communication protocols for each relationship. This works for closed, small systems. It scales poorly. And it entirely prevents the spontaneous cross-organizational collaboration that the economic logic of specialization demands.

---

## 3. Why Agent Markets Fail Differently

The discovery and trust problems are not unique to agents. Human professional services markets face both. What makes agent markets structurally different is three properties that break the informal mechanisms human markets rely on.

### 3.1 Zero-Cost Misrepresentation

In human professional services, overclaiming capability carries real costs. A consultant who misrepresents expertise suffers reputationally within their professional network — an invisible but pervasive enforcement mechanism that disciplines capability claims across the market. The social embedding of human professionals makes reputation persistent and consequential.

Agents have no social embedding. An agent can claim any capability at zero marginal cost, with no informal penalty. Milgrom (1981) shows that in competitive markets with verifiable private information, competitive pressure leads sellers to voluntarily disclose even unfavorable quality information, because silence is interpreted as the worst type — the unraveling result that restores full information in equilibrium. But this requires that quality claims be verifiable at low cost. Verifying an agent's claimed capabilities requires running actual jobs on real tasks — unlike checking a credential or calling a reference. The conditions for the unraveling result do not hold, and the market for agents exhibits the quality uncertainty dynamics identified by Akerlof (1970): without observable quality signals, low-quality agents drive out high-quality ones, and the market for the highest-quality specialist services fails to form.

### 3.2 Non-Persistent Identity

Human reputation systems work because identity is persistent. Bad behavior follows a professional across their career. An agent can be instantiated fresh, with no history, at any time. Without technical enforcement of identity — cryptographic commitment that ties an agent's history to a verifiable identifier — reputation cannot attach to an agent the way it attaches to a person or firm. The incentive to build and maintain reputation is weakened at its foundation, because reputation can be discarded at near-zero cost.

Tomašev, Franklin, and Osindero (Google DeepMind, 2026) identify this in their framework for intelligent AI delegation: current AI delegation relies on simple heuristics and cannot dynamically adapt to environmental changes or robustly handle unexpected failures. They argue that robust delegation requires "clear roles, boundaries, reputation, trust, transparency, certifiable agentic capabilities, verifiable task execution, and scalable task distribution." Each of these is a design requirement that the current agent ecosystem fails to satisfy for cross-organizational interactions. The principal-agent problem takes on heightened complexity with AI: even without hidden agendas, reward misspecification and reward hacking can cause agents to act contrary to their principal's intent in ways that are difficult to detect.

### 3.3 Dynamic Capability

Human professional credentials change slowly and predictably. An agent's capability can change overnight with a model update — between when it was evaluated and when it executes a critical job. Kapoor et al. (2025) demonstrate in the Holistic Agent Leaderboard (HAL) that scaffold choice has dramatic effects on agent performance — effects comparable in magnitude to model choice itself — yet evaluations rarely hold scaffolds constant across comparisons. Of the benchmarks they analyzed, only 2 of 9 had ever been evaluated with the same scaffold for four or more models, making cross-benchmark comparison essentially meaningless. More troubling, HAL's automated log analysis of 2.5 billion tokens of agent interactions found that agents routinely take shortcuts — searching for benchmark answers on HuggingFace instead of solving tasks — and exhibit behaviors that would be catastrophic in production deployment, including misusing credit cards in booking tasks.

The implication for specialist agent markets is direct: quality signals go stale in a way that professional credentials do not. A specialist benchmarked at 94% accuracy on a financial analysis task may perform differently after a model update, after a scaffold change, or after a shift in input distribution — with no external notification and no automatic update to the quality signals that routing systems depend on.

---

## 4. The Five Interlocking Problems

These three agent-specific market failures interact with the structural limitations of AI agents to create five interlocking problems that, taken together, prevent enterprise agent subcontracting from working at scale.

**Problem 1: The Memory Wall.** Agents fail at long jobs through context overflow, instruction dilution, error accumulation, state loss, and evaluation blindness. The 110-minute time horizon documented by METR (Kwa et al., 2025) means that jobs lasting more than a few hours — the standard unit of professional knowledge work — remain outside the reliable range of single-agent deployment. The architectural response — decomposition across multiple specialist agents — requires solving the remaining four problems simultaneously.

**Problem 2: Discovery.** No trusted, semantically searchable, quality-verified registry of specialist agents exists across organizational boundaries. Everything is hand-wired. The cost of establishing each specialist relationship manually — configuring endpoints, verifying capabilities, establishing trust — makes cross-organizational subcontracting impractical at scale and entirely prevents the spontaneous collaboration that the economic logic demands. Guo et al.'s (2025) technical framework is the most rigorous approach to existence and capability discovery; trust and quality remain unsolved.

**Problem 3: Trust and Safety.** Cross-organizational subcontracting requires that a specialist cannot exfiltrate client data, cannot contact clients through unsanctioned channels, and cannot embed sensitive information in structured outputs. Shapira et al. (2026) in *Agents of Chaos* document eleven categories of real-world agentic failures in a two-week red-teaming exercise: unauthorized compliance with non-owners, sensitive information disclosure, destructive system actions, identity spoofing, resource exhaustion, and partial system takeover. These are not edge cases — they are documented behaviors of production-grade systems operating with standard agentic tool access. Trust guarantees must be technically enforced, not contractual, because contractual enforcement after data exfiltration is inadequate.

**Problem 4: Per-Client Context.** A new specialist relationship starts from zero — no knowledge of client preferences, standing constraints, workflow patterns, or past outcomes. The platform that accumulates, across real jobs over time, which specialists this client accepts, what output formats they prefer, what data handling constraints apply, and which past outputs were revised versus accepted without change — that platform starts every new job already knowing the client. This accumulated context is unavailable to any new entrant, regardless of model quality or price. It is the durable competitive advantage.

**Problem 5: Continuous Evaluation.** Without ongoing measurement of specialist performance, routing cannot improve and specialists have unconstrained incentives to overclaim. El, Yuksekgonul, and Zou (Stanford, 2025) demonstrate that even automated meta-agent approaches to specialist design produce agents with low behavioral diversity and, in most cases, are not economically justified unless deployed across more than 15,000 examples. Human-curated specialist evaluation remains necessary. Kapoor et al. (2025) confirm that automated log analysis is essential to catch shortcuts and catastrophic behaviors that accuracy metrics alone miss. The continuous evaluation infrastructure — synthetic benchmarks, anonymized real jobs, outcome tracking, behavioral log analysis — is both necessary for routing quality and a genuine network effect: evaluation data is produced by routing volume and feeds back into routing quality.

These problems interlock. Decomposition without discovery is useless. Discovery without trust enables data exposure. Trust without context is shallow credentialing. Context without evaluation goes stale. A platform that solves four of the five provides limited value; the enterprise use cases where subcontracting matters most are exactly those where all five must be satisfied simultaneously.

---

## 5. The Platform Architecture

The appropriate response to these five problems is a **managed service** — not software tooling, not a protocol, and not a discovery directory — where enterprise client agents send complex jobs to be decomposed, routed to vetted specialists running in a sandboxed environment, verified before delivery, and refined by accumulated per-client context on every subsequent job.

The distinction between managed service and software is deliberate. Enterprise clients in the target verticals — management consulting, policy research, legal services, compliance — buy outcomes with accountability. They do not configure orchestration systems, manage specialist relationships, or maintain evaluation pipelines. The platform accepts complex jobs, returns verified outputs, and takes institutional responsibility for the process.

### 5.1 Job Intake and Decomposition

The client agent submits a complex job: a task description, relevant context, data scoped for the work, and any standing constraints (jurisdictions, data handling requirements, conflict-of-interest policies). The platform's orchestration layer decomposes the job into subtasks using a learned process informed by three inputs: the job description (via semantic embedding), the available specialist network (capability manifests ranked by current benchmark performance), and the client's context profile (which specialists have served this client well, what decompositions produced accepted outputs on similar jobs).

Decomposition is not a static template. It is an adaptive function that improves with experience. Zou et al.'s PRIME framework demonstrates that MCTS-based learned orchestration — treating decomposition strategies as options that can be selected, evaluated, and propagated back through a tree — outperforms hard-coded approaches by substantial margins. The orchestration layer is a proprietary learned component that improves with routing volume: more jobs produce better decompositions, which produce better outputs, which attract more clients.

Modular decomposition (Pan and Wu, 2025) provides the formal basis: the global task embedding is decomposed into subtask representations via attention-weighted mapping, with a global consistency mechanism ensuring that subtask boundaries are coherent and that information dependencies between subtasks are respected. An orchestrator that produces subtasks with broken dependencies or missing handoffs causes downstream failures even when individual specialists perform correctly.

### 5.2 Routing

Each subtask is matched to a specialist agent. The routing function draws on three sources of signal that must be jointly optimized:

**Capability manifests.** Structured, machine-readable descriptions of what each specialist can do, what inputs it accepts, what outputs it produces, and under what constraints it operates. This is the layer MCP provides — function signatures and capability descriptions that enable programmatic discovery. Guo et al.'s semantic profiling approach — encoding capability descriptions into a unified latent space where functionally similar but lexically different descriptions are positioned nearby — enables semantic matching between subtask requirements and specialist capabilities.

**Benchmark performance.** Platform-run evaluation scores for each specialist on the task categories they serve. These are not self-reported — they are measured by the platform using proprietary benchmark suites, synthetic tasks, and anonymized real jobs. Routing weights are a direct function of current measured performance, not historical claimed performance.

**Per-client history.** Which specialists have served this client well on similar subtasks. Which output formats this client accepts. Which specialists' reasoning styles are compatible with this client's review process. This signal is the most powerful for routing because it is specific to the client-specialist relationship in ways that aggregate benchmark scores cannot capture. It is also the signal that no new entrant can replicate.

Bansal et al. (2025) demonstrate why routing quality is the critical lever in agentic markets: their Magentic Marketplace simulation shows that frontier models approach optimal welfare under ideal search conditions but that performance degrades sharply with scale and that all models exhibit severe first-proposal bias — 10–30x advantages for the fastest-responding service agent regardless of quality. This is a market failure that quality-ranked routing directly corrects: the platform's routing function selects based on measured quality and client fit, not response speed.

### 5.3 Sandboxed Execution

Each subtask runs in an isolated container. The specialist receives only the data scoped to its specific subtask — not the full job context, not the client's broader environment, not data from other subtasks running in parallel.

The container architecture enforces the trust guarantees:

**Inference-only operation.** Specialists run in inference mode. Model weights do not update from client data. Client documents do not become training data. This is both contractual and technically enforced: the container has no mechanism for weight updates, and this is verifiable by inspection.

**Strict egress controls.** Only structured output passes the platform's verification layer. The specialist cannot transmit data through side channels, cannot embed raw client information in encoded form within outputs, and cannot contact clients directly. Egress controls are verified at the container boundary, not through monitoring of agent behavior.

**Hardware-enforced isolation for regulated data.** For tasks involving regulated non-public information — financial due diligence on private market targets, privileged legal communications, government non-public data — execution runs inside a trusted execution environment (AWS Nitro Enclaves or Intel TDX). The client receives cryptographic attestation that only approved code ran on their data, and even the platform cannot inspect the raw data inside the enclave. This closes the gap that contractual guarantees cannot: an operator who claims not to access client data can make that claim technically verifiable.

Tomašev et al. (2026) provide the theoretical framework for calibrating isolation requirements: tasks should be assessed on axes of *reversibility* (irreversible actions with external side effects require stricter isolation), *verifiability* (tasks with objectively verifiable outputs can use lighter-weight verification), and *contextuality* (high-context tasks introduce larger privacy surfaces). The platform's sandboxing architecture applies these axes dynamically: not all subtasks require full TEE isolation, and not all require the same verification depth.

### 5.4 Verification

Before any subtask output is passed to the next stage or returned to the client, it passes through verification. Kapoor et al. (2025) demonstrate that automated log analysis — not just output scoring — is essential for catching agent shortcuts and catastrophic behaviors that accuracy-only metrics miss. The platform's verification layer includes:

**Schema and format validation.** Does the output conform to the expected structure? Are required fields present? Are claimed citations present in the source data?

**Secondary validation agent.** A separate agent whose only function is to assess the primary output — checking internal consistency, verifying factual claims against provided sources, flagging anomalies. Critically, the validation agent does not share context with the primary specialist. It evaluates the output on its merits, not with the benefit of knowing what the specialist was told to produce.

**Behavioral log analysis.** Inspection of the specialist's execution trace for shortcuts — did it actually perform the requested analysis, or did it pattern-match to a cached result? Did it access the data it was supposed to access? This is the analysis that HAL demonstrates is necessary and that accuracy metrics alone cannot provide.

**Checkpoint verification for multi-stage jobs.** For long jobs decomposed into sequential stages, verification occurs at each checkpoint before the next stage begins. A failed verification triggers retry, specialist substitution, or human escalation depending on the job configuration and stakes.

### 5.5 Context Updating

After delivery, the client's context profile is updated with the signals generated by the job:

- Which specialists contributed to accepted outputs
- How the client modified or annotated the output (revision signals are more informative than binary acceptance)
- Which subtask decompositions produced coherent, accepted results
- How long the review cycle was (a signal about output quality and review friction)
- Any explicit feedback the client provides

These signals feed routing on subsequent jobs, creating a compounding improvement loop: each job makes the next job better, specifically for this client, in ways that generalize across similar job types but not across all clients indiscriminately.

---

## 6. What Specialist Agents Bring

Specialist agents in the network are not general-purpose reasoning models. Their value derives from one or more of four sources of genuine comparative advantage.

**Proprietary data access.** A specialist integrated with Bloomberg Terminal, SEC EDGAR, private market databases (PitchBook, Crunchbase Pro), or licensed academic repositories can perform research tasks that a general model cannot — because it accesses information the general model structurally lacks. This is the most durable specialist differentiator: access to data sources that cannot be replicated by calling any foundation model directly. The GDPval benchmark (Patwardhan et al., 2025) covers professional tasks requiring access to exactly these data sources — CAD design files, private sector databases, government data, licensed professional tools — confirming that the gap between general models and data-integrated specialists is real and persistent for professional-grade work.

**Specialized tooling.** Financial modeling platforms, statutory legal databases, clinical trial registries, regulatory compliance monitoring systems — specialists deeply integrated with specific tooling produce outputs that general models cannot produce from text alone. The tool access is not incidental; it is the mechanism by which the specialist adds value.

**Domain-optimized performance.** Fine-tuned models or heavily optimized systems for specific domains demonstrably outperform general models on narrow task classes. El et al.'s (Stanford, 2025) finding that meta-agent approaches produce low behavioral diversity — designed agents tend to converge on similar strategies rather than genuinely specializing — is an argument for human-curated specialist design: diverse, genuine specialists are not produced automatically and require deliberate selection.

**Certified and accountable outputs.** In regulated industries, outputs that carry platform certification — attestations that outputs were produced by an evaluated, audited, sandboxed process — have legal and compliance value that a general model call cannot provide. This certification is a product, not a feature: it is what allows the output to be used in regulatory filings, due diligence reports, and legal proceedings without independent re-verification.

Liu (2026) notes that in an agent-oriented market, the durable supplier "is not the one with the loudest brand but the one with the cleanest machine interface and the best measured performance." Sustainable specialists sell what the agent cannot cheaply reproduce on its own. The platform's role is to identify, vet, and continuously measure which specialists genuinely have this comparative advantage.

---

## 7. The Institutional Stack: Where This Platform Sits

Understanding the platform's position requires understanding the full emerging stack of agentic infrastructure.

| Layer | What it provides | Who is building it |
|---|---|---|
| Foundation models | Core reasoning capability | Anthropic, OpenAI, Google, Meta |
| Agent frameworks | Building and orchestrating individual agents | LangGraph, CrewAI, AutoGen |
| Memory infrastructure | Per-agent persistent memory within an organization | Mem0, Letta, Zep |
| Agent clouds | Managed infrastructure for running your own agents | AWS AgentCore, Azure AI Foundry, Vertex |
| Agent builders | No-code agent creation and hosting | MindStudio, Relevance AI |
| Discovery protocols | Standardized capability description and invocation | MCP, A2A, ANP |
| Payment rails | Agent-to-agent payment settlement | x402 (Coinbase), MPP (Stripe) |
| **Enterprise trust layer** | **Vetted cross-organizational subcontracting as a managed service** | **This platform** |

The enterprise trust layer row is genuinely empty. None of the companies building the layers above provide managed, verified, cross-organizational agent subcontracting with per-client context accumulation. Each layer is necessary; none is sufficient.

Deng et al. (2025) frame this in their Agentic Services Computing (ASC) paradigm: agentic services must be understood through a full lifecycle — design, deployment, operation, evolution — with trustworthiness as a cross-cutting commitment across all phases, not an add-on at the end. The platform is an ASC instantiation focused specifically on the enterprise trust dimension of cross-organizational operation.

**Complementary, not competitive.** The platform is not competing with MCP, AWS AgentCore, Mem0, or MindStudio. It is the layer that makes those tools safe to use at enterprise scale across organizational boundaries. A MindStudio-hosted specialist could participate in the platform's vetted network. An enterprise client already using AgentCore for internal orchestration would use the platform for external specialist subcontracting. MCP serves as the invocation protocol for specialists once they have been discovered, vetted, and routed by the platform. The stack is additive.

---

## 8. The Moat: Per-Client Context as Compound Advantage

Infrastructure gets commoditized. Foundation models improve continuously and drive down the marginal cost of reasoning. Technical advantages in orchestration, sandboxing, and protocol support are replicable by better-funded competitors. Any purely technical moat in this space is temporary.

The durable competitive advantage is accumulated per-client context.

After twelve months of real work for a management consulting client:

The platform knows which specialists produce outputs this client accepts without revision. It knows the standing constraints: jurisdictions covered, data sensitivity classifications, citation format requirements, conflict-of-interest policies for named entities. It knows the workflow: review cycle length, the seniority levels that approve different output types, escalation patterns when specialists disagree. It knows which past subtask decompositions produced accepted outputs on similar job types and which decompositions required rework. It knows the revision patterns: where clients edit systematically, which signals distinguish acceptable outputs that required minor polish from outputs that needed substantive correction. And it knows which revision patterns are client-specific rather than specialist-specific, enabling the platform to pre-correct for client-specific preferences.

A new entrant — regardless of model quality or price — starts at zero with this client. The platform starts every new job already knowing the client in a way that cannot be transferred, purchased, or reverse-engineered.

This is the same structure that Guo et al. (2025) describe as "memory-enhanced continual discovery" — the component of their IoA framework where past interactions improve future matching. Their insight, applied to the enterprise context, is that discovery quality compounds with history. The platform's per-client context is exactly this compounding discovery quality, made specific to each client-specialist relationship rather than averaged across all interactions.

The compound advantage is also non-transferable in both directions. A client who leaves loses their accumulated context; a competitor cannot offer equivalent starting conditions. A specialist who performs well for a specific client builds a history that improves its routing weight for that client; a competing specialist starting fresh cannot match that performance record immediately, even if its underlying capabilities are equivalent.

---

## 9. The Continuous Evaluation Engine

The platform's routing quality depends on honest performance data about specialists. The three market failures identified in Section 3 mean that self-reported quality claims are unreliable and that static evaluations go stale as model versions change. The continuous evaluation engine is the formal substitute for the informal quality mechanisms that exist in human professional markets.

**Synthetic benchmarks.** The platform maintains proprietary benchmark suites for each task category in the specialist network. These are known-answer tasks drawn from public sources, processed from real jobs, and designed to probe specific capability dimensions relevant to the specialist's claimed domain. Specialists are evaluated against these benchmarks continuously. Results are proprietary to the platform — specialists see scores but not underlying tasks, preventing benchmark-specific overfitting. Results feed routing weights directly.

**Anonymized real jobs.** Successful real job outputs, stripped of client-identifying information and processed to remove any recoverable private data, become benchmark tasks. Specialists competing on these tasks do not know they are being evaluated against former real jobs. This prevents the divergence between benchmark performance and real-job performance that the HAL evaluation (Kapoor et al., 2025) documents across current public benchmarks.

**Outcome tracking.** Client acceptance, revision, and rejection signals provide the strongest ground-truth signal about specialist-client fit. The platform tracks long-run outcomes with careful attention to gaming: simple acceptance rates are gameable; revision-weighted acceptance rates, revision type classification, and longitudinal outcome tracking are harder to game and more informative.

**Behavioral log analysis.** Following the methodology demonstrated by HAL (Kapoor et al., 2025), automated analysis of specialist execution logs catches shortcuts — pattern-matching to cached results rather than performing requested analysis — and early-warning signals of degraded performance. Log analysis runs on every job, not just on periodic evaluation cycles.

**Staked reputation.** Specialists whose claimed capabilities significantly exceed their measured performance face reduced routing and eventual removal from the network. The economic cost of overclaiming is real and continuous. This converts the honor system of self-reported capabilities into a market with selection pressure — specialists that perform well get more routing volume; specialists that underperform lose routing volume until performance recovers or they exit the network.

The continuous evaluation system is also a network effect: evaluation data is produced by routing volume, and better evaluation data produces better routing, which attracts more clients, which produces more routing volume. The evaluation engine improves as the platform scales in a way that a competitor starting fresh cannot immediately match.

---

## 10. The Wedge: Management Consulting and Policy Research

Enterprise trust layers require enterprise clients who have acute pain, genuine sensitivity requirements, and budget. The first clients must be in verticals where three conditions hold simultaneously: the memory wall is acutely limiting, the trust story is a feature rather than a friction, and buyers understand the value of quality over speed.

Management consulting and policy research satisfy all three conditions.

**Memory wall acuity.** A consulting team conducting an industry competitive analysis must synthesize regulatory filings, patent databases, private market data, news archives, academic literature, and client-provided confidential materials — across forty or more companies, over weeks. GDPval (Patwardhan et al., 2025) confirms that these are precisely the task types where frontier models approach expert quality but require structured multi-hour workflows to do so. The memory wall is the binding constraint. A decomposed, specialist-routed approach can complete these jobs at a quality and speed that a single-agent deployment cannot.

**Trust as a feature.** Consulting firms handle non-public client information — strategic plans, M&A targets, proprietary competitive intelligence. Policy research institutions handle sensitive government data, restricted survey data, and pre-publication research. Both have compliance obligations, professional responsibility requirements, and reputational stakes that make sandboxed execution, verified outputs, and attestable data handling not merely acceptable but actively desirable. A general model call cannot provide these guarantees. The platform's trust architecture is a differentiated feature in this market.

**Budget and urgency.** Senior consultants and research directors at well-funded institutions are not price-sensitive for tools that measurably improve output quality and reduce turnaround on consequential projects. The ROI calculation is favorable: if the platform enables a two-person team to produce the output of a five-person team on complex multi-source research, the subscription economics are straightforward for the buyer.

The entry motion is not a broad marketplace launch. It is signing two or three pilot clients in these verticals, building deep context profiles for their specific work patterns, and demonstrating measurable quality improvement on real jobs. Pilot clients serve three functions: generating the initial specialist evaluation data, validating the per-client context accumulation model, and providing the case studies that justify expansion to adjacent verticals.

---

## 11. The Institutional Design Problem

The platform described here is, at its core, a market design problem. The economics of agent specialization create demand for cross-organizational subcontracting. The three market failures identified in Section 3 prevent that market from forming through informal mechanisms. The platform must substitute formal institutional mechanisms — evaluation, identity enforcement, verification, accountability — for the informal mechanisms that human professional markets rely on.

Liu (2026) frames the dual architecture requirement precisely: a viable agent-oriented market must simultaneously reduce exchange friction below the threshold at which delegation dominates self-computation, and embed governance mechanisms sufficient to make delegated action trustworthy and auditable. Markets that optimize only for the first condition generate activity but cannot retain enterprise clients facing real compliance and liability exposure. Markets that optimize only for the second condition are too slow and expensive to compete with general model calls.

The institutional design choices that determine whether this balance is achieved:

**Verification before trust, not trust before verification.** Specialists enter the network through an evaluation process, not a self-registration process. The platform verifies capability claims before routing volume — not after problems emerge. This differs from most current discovery systems, where listing is self-service and verification happens, if at all, after reputation accumulates through user feedback.

**Reputation as infrastructure, not marketing.** The evaluation system produces routing-relevant performance data — numbers that directly determine routing weights and economic position in the network — not review stars that decorate a profile page. Specialists compete on measured outcomes that have immediate economic consequences.

**Context as the primary service, not a feature.** Per-client context accumulation is not a convenience improvement to a commodity routing service. It is the primary value delivery mechanism and the primary moat. The architecture prioritizes context accumulation from the first interaction: every job is an investment in the client relationship as much as a delivery of current output.

**Governance architecture for the long run.** Rothschild et al.'s warning about agentic walled gardens applies to platform design as well as market structure: a platform that becomes too dominant in cross-organizational agent routing has the same incentive to restrict openness and extract rents that dominant platforms in adjacent markets have exercised. The institutional design of the platform should include governance commitments — specialist appeal mechanisms, transparent routing criteria, published evaluation methodologies — that constrain this tendency before it becomes a political liability.

---

## 12. Open Questions and Strategic Risks

This paper describes a thesis under development. The most important unresolved questions are not technical — they are strategic and institutional.

**The bootstrap problem.** The platform needs evaluation data to route correctly, but needs routing volume to generate evaluation data. The resolution is to seed the specialist network with in-house specialists initially, run real pilot jobs, and generate the first evaluation data through controlled execution before opening to third-party specialists. But the optimal sequencing — when to open the specialist network, how many specialists are needed before routing quality is defensible, how to price during the bootstrap phase — requires empirical validation.

**The foundation model substitution risk.** If frontier models continue to improve rapidly, the gap between general model performance and specialist performance on many task types will narrow. METR's (2025) 7-month doubling time on task-completion time horizons is the most important external parameter for this business. If that doubling continues or accelerates, the platform has years — perhaps a decade — before raw model capability closes the gap on most professional knowledge work tasks. But the platform's moat must compound faster than model improvement erodes it. The argument is that per-client context and institutional trust are model-agnostic — the platform works regardless of which model underlies each specialist, and the per-client context advantage increases rather than decreases as models improve and clients delegate more. But this argument requires empirical validation, not just theoretical assertion.

**Specialist incentive design.** What makes a high-quality specialist choose to participate in the vetted network rather than go direct to clients? The answer must involve volume advantages (the platform provides more routed jobs than direct relationships), trust advantages (the platform's verification and sandboxing protects both sides of the transaction), and economic advantages (the platform's routing efficiency increases specialist utilization). The exact incentive structure, and which benefits dominate for which specialist types, requires careful empirical testing.

**Self-improving specialists.** Zhang et al.'s Darwin Gödel Machine (2025) demonstrates that agents can improve themselves through open-ended evolutionary self-modification, increasing SWE-bench performance from 20% to 50% autonomously. If specialist agents can self-improve, the gap between a specialist that performed well last month and one that has evolved since is itself a capability verification problem. The continuous evaluation engine must run frequently enough to catch self-improvement curves, and the platform must maintain clear versioning of which specialist capability was evaluated at which point.

**The vertical expansion sequence.** Management consulting and policy research are the proposed first vertical. Legal research, compliance monitoring, financial services due diligence, and clinical research are natural adjacencies. The sequencing should be driven by specialist network reuse — specialists that serve consulting clients on competitive intelligence tasks may also serve legal clients on industry research tasks, reducing the bootstrap cost of each new vertical. Mapping the specialist network topology in advance determines which verticals can be entered cheaply.

---

## 13. Conclusion

The economic logic of agent specialization is compelling, the research evidence for its near-term feasibility is strong, and the infrastructure gap is genuinely empty. The agents that enterprises deploy today are capable of remarkable bounded tasks; the class of consequential long-running knowledge work that represents the most valuable professional output remains outside what any single agent can reliably produce.

The architectural response — decomposing complex jobs across specialist agents — is validated by multiple independent research directions: PRIME's MCTS-based learned orchestration, Pan and Wu's modular decomposition framework, Piskala's control-axis taxonomy, and Chen et al.'s IoA framework all converge on the same structure. The technical components exist. The missing piece is the institutional infrastructure that makes cross-organizational specialist routing trustworthy at enterprise scale.

That infrastructure — verified capability claims, enforced data isolation, continuous performance measurement, accumulated per-client context — is what this platform provides. It is not a technology platform in the sense of infrastructure to be configured. It is an institutional platform in the sense of a market institution that substitutes formal verification for the informal trust mechanisms that agent markets structurally cannot provide on their own.

Rothschild et al. conclude that "the architecture of agentic communication will determine the extent to which generative AI democratizes access to economic opportunity." The enterprise trust layer is part of that architecture — the institutional component that determines whether cross-organizational agent collaboration remains a vision or becomes an operational reality.

---

## References

Akerlof, G. (1970). The Market for Lemons: Quality Uncertainty and the Market Mechanism. *Quarterly Journal of Economics*, 84(3), 488–500.

Bansal, G., Hua, W., Huang, Z., Fourney, A., Swearngin, A., Epperson, W., Payne, T., Hofman, J.M., Lucier, B., Singh, C., Mobius, M., Nambi, A., Yadav, A., Gao, K., Rothschild, D.M., Slivkins, A., Goldstein, D.G., Mozannar, H., Immorlica, N., Murad, M., Vogel, M., Kambhampati, S., Horvitz, E., and Amershi, S. (2025). *Magentic Marketplace: An Open-Source Environment for Studying Agentic Markets*. Microsoft Research. arXiv:2510.25779.

Becker, G.S. and Murphy, K.M. (1992). The Division of Labor, Coordination Costs, and Knowledge. *Quarterly Journal of Economics*, 107(4), 1137–1160.

Chen, W., You, Z., Li, R., Guan, Y., Qian, C., Zhao, C., Yang, C., Xie, R., Liu, Z., and Sun, M. (2024). *Internet of Agents: Weaving a Web of Heterogeneous Agents for Collaborative Intelligence*. Tsinghua University / Peking University. arXiv:2407.07061.

Deng, S., Zhao, H., Wang, Z., Cheng, G., Chen, P., Qian, W., Ling, Z., Yin, J., Zomaya, A.Y., and Dustdar, S. (2025). *Agentic Services Computing*. Zhejiang University / University of Sydney / TU Wien. arXiv:2509.24380.

El, B., Yuksekgonul, M., and Zou, J. (2025). *Inefficiencies of Meta Agents for Agent Design*. Stanford University.

Guo, S., Wang, Y., Su, Z., Pan, Y., Hu, Q., and Luan, T.H. (2025). *Agent Discovery in Internet of Agents: Challenges and Solutions*. Xi'an Jiaotong University. arXiv:2511.19113.

Kapoor, S., Stroebl, B., Ndzomga, F., Oruganty, D., and others. (2025). *Holistic Agent Leaderboard: The Missing Infrastructure for AI Agent Evaluation*. Princeton University / Stanford University. arXiv:2510.11977.

Kwa, T., West, B., Becker, J., Deng, A., Garcia, K., Hasin, M., Jawhar, S., Kinniment, M., Rush, N., Von Arx, S., and others. (2025). *Measuring AI Ability to Complete Long Software Tasks*. Model Evaluation & Threat Research (METR). arXiv:2503.14499.

Liu, J.H. (2026). *Building an AI Agent-Oriented Market: Institutional Design, Protocol Economics, and Governance for Machine-Native Trade*. Medium.

Liu, N.F., Lin, K., Hewitt, J., Paranjape, A., Bevilacqua, M., Petroni, F., and Liang, P. (2023). *Lost in the Middle: How Language Models Use Long Contexts*. Stanford University / UC Berkeley / Samaya AI. arXiv:2307.03172.

Milgrom, P. (1981). Good News and Bad News: Representation Theorems and Applications. *Bell Journal of Economics*, 12(2), 380–391.

MindStudio Team (2026a). *AI Agent Memory Wall: Why Agents Fail at Long-Running Jobs and How to Fix It*. MindStudio Blog. March 21, 2026.

MindStudio Team (2026b). *What Is the Agent Discovery Problem? Why AI Agents Need an App Store to Find Each Other*. MindStudio Blog. April 10, 2026.

Pan, S. and Wu, D. (2025). *Modular Task Decomposition and Dynamic Collaboration in Multi-Agent Systems Driven by Large Language Models*. Carnegie Mellon University / University of Southern California.

Patwardhan, T., Dias, R., Proehl, E., Kim, G., Wang, M., Watkins, O., Fishman, S.P., Aljubeh, M., Thacker, P., and others. (2025). *GDPval: Evaluating AI Model Performance on Real-World Economically Valuable Tasks*. OpenAI. arXiv:2510.05374.

Piskala, D.B. (2026). *Agent, Sub-Agent, Skill, or Tool? A Practitioner's Guide to Extending Agentic AI Systems*. TechRxiv.

Rothschild, D., Mobius, M., Hofman, J., Dillon, E., Goldstein, D., Immorlica, N., Jaffe, S., Lucier, B., Slivkins, A., and Vogel, M. (2025). *The Agentic Economy*. Microsoft Research. arXiv:2505.15799.

Shapira, N., Wendler, C., Yen, A., Sarti, G., Pal, K., Floody, O., and others. (2026). *Agents of Chaos*. arXiv:2602.20021.

Tomašev, N., Franklin, M., and Osindero, S. (2026). *Intelligent AI Delegation*. Google DeepMind. arXiv:2602.11865.

Zhang, J., Hu, S., Lu, C., Lange, R., and Clune, J. (2025). *Darwin Gödel Machine: Open-Ended Evolution of Self-Improving Agents*. University of British Columbia / Vector Institute / Sakana AI. Published as a conference paper at ICLR 2026. arXiv:2505.22954.

Zou, C., Liu, S., and Khankari, J. (2025). *PRIME: Planning with Reflective, Iterative, Multi-agentic Exploration*. Stanford University.

---

*This white paper is a working document synthesizing ongoing research. Last updated: 2026-04-23.*
