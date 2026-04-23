---
title: "Building an AI Agent-Oriented Market: Institutional Design, Protocol Economics, and Governance for Machine-Native Trade"
source: "https://medium.com/@gwrx2005/building-an-ai-agent-oriented-market-institutional-design-protocol-economics-and-governance-for-ebeb2f103555"
author:
  - "[[Jung-Hua Liu]]"
published: 2026-03-09
created: 2026-04-22
description: "This paper studies how to build an AI agent-oriented market in which software agents, rather than humans, become the dominant buyers of digi"
tags:
  - "clippings"
---
## Abstract

This paper studies how to build an AI agent-oriented market in which software agents, rather than humans, become the dominant buyers of digital services. The core research question is institutional rather than merely technical: what market architecture causes autonomous agents to prefer external trade over internal computation, and what governance mechanisms are required to make such trade durable at scale? The study combines published research on agentic markets and governance, especially Shapira et al. (2026), Malone et al. (1987), Bakos (1997), Yang et al. (2025), and Bansal et al. (2025), with a Dockerized prototype simulation of machine-native procurement. The project runs 7,680 policy-and-task scenarios over a machine-readable service registry and records whether an autonomous buyer can successfully route work to market suppliers under explicit budget, latency, verification, compliance, real-time, and whitelist constraints. Across these runs, the prototype selects an external supplier in 65.4% of cases, yields an average selected price of $0.0074 per call and average selected latency of 0.219 seconds, and delivers mean workflow gains of roughly 90.8x in time and 40.3x in cost relative to the configured self-compute baseline. At the same time, 34.6% of scenarios are blocked, with GPU-intensive tasks showing only a 10% trade rate under the modeled policy grid. These results support a central thesis: agent-oriented markets emerge when protocol-level discoverability, pricing, authentication, telemetry, and governance metadata reduce the cost of delegation below the cost of self-computation for specific task classes. However, Shapira et al. (2026) show that autonomy without control introduces severe vulnerabilities, implying that market efficiency alone is insufficient. The paper argues that a viable agent-native market requires a dual architecture: frictionless machine-readable exchange on the one hand, and verifiable governance, sandboxing, accountability, and reputation on the other. The contribution of the paper is a design framework for agent-oriented markets that combines transaction-cost economics, market microstructure, API governance, and reproducible prototype-run evidence.

[https://github.com/gwrxuk/agent\_market](https://github.com/gwrxuk/agent_market)

## Keywords

AI agents; agent-oriented markets; machine-readable pricing; transaction cost economics; API marketplaces; autonomous trade; protocol governance; agent-native commerce

## 1\. Introduction

For most of modern digital commerce, the market has been designed around the perceptual and cognitive limitations of humans. Search engines index pages for people to browse. Marketing teams optimize landing pages, social proof, and brand narratives for human attention. Sales organizations convert prospects through demonstrations, relationship-building, and negotiation. Pricing is often displayed on websites or hidden behind sales contact forms because the buyer is presumed to be a person whose decision process is interpretive, social, and only partly calculative. Even when software participates in e-commerce, it usually acts as infrastructure serving human intentions. The user remains the final economic agent.

That assumption is now unstable. Autonomous AI agents can search, compare, reason, invoke tools, access APIs, and execute tasks on behalf of users or organizations. The important change is not simply that AI can automate more work. It is that AI can increasingly become the buyer, evaluator, and coordinator of services. When the buyer is software rather than a human, the informational environment of the market changes. Brand salience matters less. Narrative persuasion matters less. Latency, reliability, price transparency, machine-readable capability descriptions, policy constraints, and programmatic payment matter more. The commercial interface shifts from persuasive representation to protocol design.

The question, then, is not whether AI agents can purchase services. They already can in narrow settings. The deeper question is how to construct a market institution that attracts agents to trade rather than to compute internally. This is a Coasean problem in a new form. Ronald Coase asked why firms exist when markets can, in theory, coordinate production. His answer centered on transaction costs: firms substitute internal managerial coordination for the frictions of using the external market. In agentic systems, however, the boundary between internal computation and external exchange becomes dynamic. An agent can decide, task by task, whether to reason locally, call a general model, use a cached workflow, or buy a specialist service from the open market. The “firm boundary” becomes an algorithmic decision boundary.

Electronic-market theory and emerging agent-marketplace research sharply frame this shift (Malone et al., 1987; Bakos, 1997; Yang et al., 2025; Bansal et al., 2025). These works imply that AI agents can drive search and evaluation costs downward because a machine can query structured registries, compare service attributes algorithmically, and select among options without browsing or emotional bias. They also suggest that the services most attractive to agents are not those with the strongest brands, but those that offer machine-readable discovery, protocol-compatible pricing, low-latency execution, and high reliability. In this picture, the next commercial internet layer is not optimized for human browsing but for agent procurement.

At the same time, Shapira et al. (2026) document how autonomous agents operating in live environments exhibit serious security, privacy, and governance failures. The paper describes red-teaming over a two-week period with twenty AI researchers and reports eleven case studies involving unauthorized compliance, sensitive-information disclosure, destructive system actions, denial-of-service behavior, identity spoofing, unsafe practice propagation, and partial system takeover. This source complicates any simple narrative of agentic commerce. If agents are to become market participants, the market must not merely minimize transaction costs. It must also survive adversarial behavior, delegation ambiguity, unsafe tool use, and failures of truthfulness or control.

This study therefore treats agent-oriented market design as a joint problem of economics and governance. A market that reduces the friction of machine-to-machine trade but fails to establish trust, auditability, and bounded autonomy will not attract durable agent demand, especially in enterprise settings. Conversely, a heavily governed market that preserves too much friction will fail to outcompete self-computation or closed ecosystems. The practical challenge is to find the institutional design that satisfies both conditions: lower decision and integration costs than in-house computation, and higher verifiability than unregulated tool use.

To address that challenge, this paper makes two contributions. First, it develops a conceptual framework for agent-oriented market design by synthesizing transaction-cost economics, platform design, and protocol-level service architecture. Second, it operationalizes that framework through a Dockerized prototype-and-simulation pipeline that runs market-selection scenarios and produces reproducible charts from the resulting routing outcomes. The resulting analysis does not claim to provide a final theory of agentic markets. Instead, it offers an exploratory but structured account of how such markets can be built, why agents would choose them, and what institutional safeguards they require.

The rest of the paper proceeds as follows. Section 2 reviews the relevant literature across organizational economics, electronic markets, platform theory, LLM-based agents, and AI governance. Section 3 develops the theoretical framing and clarifies how an agent-oriented market differs from a human-facing digital marketplace. Section 4 explains the research design and the Dockerized analytics workflow used to run prototype-based market simulations. Section 5 presents the main findings on make-or-buy economics, market architecture, and reliability bottlenecks. Section 6 integrates the governance lessons from *Agents of Chaos* and proposes a layered design for safe agent-native exchange. Section 7 develops a practical design framework for market builders. Section 8 discusses implications for firms, API providers, and regulators. Section 9 concludes with a research agenda for machine-native commerce.

## 2\. Literature Review

The literature relevant to agent-oriented markets spans at least four domains: the theory of the firm and transaction-cost economics, research on electronic and platform-mediated markets, technical work on LLM-based agents, and governance scholarship on AI risk. Reviewing these streams is important because no single field, by itself, adequately explains machine-native trade.

The first stream begins with the economics of organization. Coase’s classic argument that firms exist because using markets is costly remains the foundational starting point for any analysis of agent make-or-buy behavior (Coase, 1937). Simon’s theory of bounded rationality further clarifies why decision procedures matter: even when optimization is desirable in theory, actual decision-makers face information and computation constraints (Simon, 1955). Williamson later formalized transaction cost economics by treating the transaction itself as the unit of analysis and by showing how uncertainty, frequency, and asset specificity shape efficient governance structures (Williamson, 1981). Jensen and Meckling added an agency perspective, reminding us that delegation produces control and monitoring problems even when specialization is economically attractive (Jensen & Meckling, 1976). Taken together, these works imply that an agent-oriented market cannot be explained only by lower prices; it must also be analyzed as a new governance regime for delegated action.

The second stream studies how information technology changes coordination structures. Malone, Yates, and Benjamin argued that digital systems reduce coordination costs and can therefore shift activity from hierarchies toward electronic markets (Malone et al., 1987). Bakos later showed more specifically that electronic marketplaces can reduce buyer search costs and improve market efficiency, especially where differentiated products and information asymmetries previously limited competition (Bakos, 1997). Brynjolfsson and Smith complicated the early “frictionless commerce” thesis by showing that even online markets with lower search costs still exhibit price dispersion and branding effects (Brynjolfsson & Smith, 2000). Varian, in turn, described internet commerce as a world of computer-mediated transactions in which modular digital components radically accelerate combinatorial innovation (Varian, 2010). This literature is highly relevant to agentic markets because it shows that lower information frictions do not eliminate institutions; rather, they reorganize them around new cost structures.

Closely related is the literature on platforms, standards, and network effects. Katz and Shapiro demonstrated why compatibility decisions matter in markets with network externalities (Katz & Shapiro, 1985), while Farrell and Saloner showed that standardization can both generate coordination benefits and create inertia around inferior designs (Farrell & Saloner, 1985). Rochet and Tirole provided the canonical economic treatment of platform competition in two-sided markets, emphasizing that intermediaries must attract and govern multiple sides simultaneously (Rochet & Tirole, 2003). Rysman synthesized this literature for economists and highlighted its implications for platform pricing, matching, and regulation (Rysman, 2009). Eisenmann, Parker, and Van Alstyne translated similar insights into strategy, showing how two-sided intermediaries must solve chicken-and-egg problems in ecosystem formation (Eisenmann et al., 2006). Boudreau further demonstrated that opening a platform can accelerate innovation, but that the structure of access and control matters materially (Boudreau, 2010). Dellarocas, finally, examined reputation and feedback mechanisms as trust infrastructure in online markets (Dellarocas, 2003). This body of work suggests that an agent-oriented market will succeed only if it solves compatibility, standardization, ecosystem liquidity, and trust update problems in a machine-readable form.

The third stream concerns AI agents themselves. Recent LLM-based agent research moves beyond static text generation toward systems that plan, act, invoke tools, and coordinate over multiple steps. ReAct is a foundational example because it explicitly links reasoning traces with tool-using behavior, thereby making action selection part of the model’s runtime loop rather than a purely offline inference problem (Yao et al., 2023). Mialon et al. synthesize a broader landscape of augmented language models that use retrieval, tools, and external modules to overcome the limits of stand-alone generation (Mialon et al., 2023). Park et al.’s generative agents work, although oriented toward social simulation, demonstrates how memory, reflection, and planning can produce coherent agent behavior over time (Park et al., 2023). Xi et al. survey the broader rise of LLM-based agents and organize the field around perception, planning, and action components (Xi et al., 2023). Li’s survey on LLM-based agents focuses on reusable workflows and common architectural components, which is especially useful when thinking about market-facing interoperability rather than just benchmark performance (Li, 2024). Guo et al. extend the analysis to multi-agent systems, where communication, role specialization, and collective capacity become first-order design variables (Guo et al., 2024). Across this technical literature, one common message stands out: once models can invoke tools reliably, external services become part of the agent’s native problem-solving substrate rather than an exceptional add-on.

The fourth stream addresses governance and risk. Bommasani et al. argue that foundation models create systemic downstream effects because many applications inherit common capabilities and common failure modes from shared model bases (Bommasani et al., 2021). Weidinger et al. provide a taxonomy of risks posed by language models, showing that misuse, misinformation, information hazards, and human-computer interaction harms are not incidental edge cases but recurring structural concerns (Weidinger et al., 2022). The NIST AI Risk Management Framework translates such concerns into operational governance functions for mapping, measuring, and managing AI risks (NIST, 2023). The most directly relevant source for this paper is *Agents of Chaos*, which provides empirical evidence that autonomous agents operating with tools, memory, communication channels, and shell access can display unsafe delegation, sensitive-information leakage, identity spoofing, destructive actions, and false claims of task completion (Shapira et al., 2026). This governance literature matters because a market populated by autonomous buyers and autonomous sellers is not simply more efficient software commerce. It is a more deeply delegated socio-technical system whose failures may propagate faster than in traditional digital markets.

The reviewed literature leaves an important gap. Transaction-cost and platform scholars explain why lower coordination costs shift market boundaries, but they do not analyze autonomous software buyers in detail. Agent-systems researchers explain how LLM agents plan and use tools, but they typically do not theorize market microstructure, pricing protocols, or ecosystem governance. AI governance work identifies risks, but it rarely explains how market design can simultaneously enable high-frequency exchange and bound delegated authority. This paper addresses that gap by connecting these four traditions to a reproducible prototype simulation: agent-oriented markets emerge when technical tool-use capacity intersects with low-friction market infrastructure, but they become durable only when verifiability and governance scale at the same rate as delegation.

## 3\. Theoretical Framing: From Human-Attention Markets to Agent-Native Exchange

An agent-oriented market may be defined as a market whose primary buyers are autonomous or semi-autonomous software agents that select, procure, and coordinate services using explicit computational objectives and machine-readable constraints. This is not simply an API marketplace with better documentation. It is a market where the demand side is structurally different. The buyer does not browse. The buyer queries. The buyer does not infer prices from a webpage. The buyer expects prices in a schema. The buyer does not weigh persuasive branding against utility. The buyer optimizes across cost, latency, reliability, and policy compliance. This change in buyer ontology reshapes market structure.

Electronic-market theory, platform economics, and current agent-system research together imply that traditional marketing loses force under these conditions (Bakos, 1997; Rochet & Tirole, 2003; Li, 2024; Yang et al., 2025). Human-facing commerce treats attention as a scarce asset. Firms spend heavily on search optimization, visual design, content marketing, social proof, and emotional positioning because human decision-making is bounded, distracted, status-sensitive, and susceptible to framing effects. By contrast, an AI agent evaluates suppliers through deterministic or probabilistic functions over structured attributes. If capability descriptions, service-level statistics, pricing schedules, and policies are visible in machine-readable form, then choice becomes an optimization problem rather than an attention problem. The commercial surface shifts from brand-mediated persuasion to measurable performance.

This does not mean that all non-price differentiation disappears. It means that differentiation must be translated into variables that software can parse and evaluate. Trust becomes uptime history, benchmark scores, provenance records, security attestations, and signed policy metadata. Reputation becomes a machine-readable prior updated by observed outcomes. Quality becomes a probability distribution over successful task completion. Compliance becomes a set of constraints encoded in access policies, data residency statements, and usage licenses. In other words, the symbolic and narrative functions long performed by branding are transformed into observable metrics and executable rules.

From a Coasean perspective, the agent’s make-or-buy decision is the key analytic unit. A human organization historically internalized tasks when market exchange was too slow, costly, or uncertain. An agent does something analogous but at much smaller temporal scales. For each subtask, it can ask whether internal reasoning or external procurement yields the higher expected utility under budget, latency, and risk constraints. If external specialist services are cheaper, faster, and more reliable than local computation, the equilibrium outcome is greater outsourcing. If they are expensive, unreliable, or difficult to integrate, the agent will compute locally or remain within a closed tool bundle.

The prototype simulation provides an explicit numeric illustration of this threshold. Using a self-compute baseline configured at $0.300 and 17.5 seconds per call, the Dockerized pipeline runs procurement scenarios against specialist services that expose machine-readable prices, latency, reliability, compliance, and onboarding metadata. Across all successful market selections, the chosen route averages $0.0074 per call and 0.219 seconds of latency. Even allowing for simplification, the implication is straightforward: when a specialist endpoint supplies a relevant answer at roughly one-fortieth the cost and around one-eightieth the latency, the market becomes the rational default for the tasks it can credibly serve.

Yet economic superiority alone does not settle the institutional question. The agent still needs discoverability, authentication, payment, verification, and policy compatibility. These are themselves transaction costs, though of a new sort. What matters is not simply the price of the service but the total friction of machine-to-machine exchange. A service that is cheap per call but requires a human to create an account, copy API keys from a dashboard, negotiate terms with sales, and manually approve scopes is not truly available to an autonomous agent. The integration burden reintroduces transaction costs in another form. Thus, agent-oriented markets require that market participation itself be machine-native.

The literature on digital platforms often emphasizes network effects, liquidity, and standardization. Those features remain relevant here, but they must be reinterpreted. Network effects depend not on the number of human users but on the density and interoperability of machine-readable services, credentials, policy standards, and evaluation records. Liquidity depends not merely on listing many sellers but on ensuring that enough of those sellers are callable, reliable, and semantically legible to agents. Standardization becomes critical because heterogeneous schemas, opaque pricing, or bespoke onboarding flows sharply raise machine integration costs.

At the same time, the agentic market is not frictionless. The source paper *Agents of Chaos* reminds us that autonomous agents may act unsafely, accept instructions from the wrong principal, leak sensitive information, or cause destructive effects through tool use. If buyers themselves are autonomous systems, then demand-side risk is endogenous to market design. Market institutions must defend not only honest buyers from malicious sellers, but also systems from compromised or misaligned agents acting as buyers. This introduces a governance layer largely absent from traditional API marketplaces.

The theoretical implication is that a viable agent-oriented market must satisfy two conditions simultaneously. First, it must reduce exchange friction below the threshold at which delegation dominates self-computation. Second, it must embed governance mechanisms sufficient to make delegated action trustworthy and auditable. The first condition generates market activity. The second sustains it.

## 4\. Research Design and Dockerized Analytic Workflow

This paper uses an exploratory mixed-method design centered on published literature and a project-specific prototype simulation. The core scholarly source for governance is Shapira et al. (2026), *Agents of Chaos*. In this study, that source is treated as literature for the governance argument, while the empirical layer comes from running the agent-market prototype itself as a simulation environment rather than treating citation files as empirical datasets.

The simulation environment consists of a machine-readable service registry, a self-compute baseline, a policy grid, and a scoring function shared with the prototype interface. Each service exposes price, latency, reliability, confidence, verification status, compliance status, real-time availability, whitelist status, onboarding requests, and task-fit values. The scenario grid spans four task types (web\_retrieval, private\_data, gpu\_compute, and verified\_decision), six budget levels, five latency ceilings, four workflow lengths, and four binary governance controls for verification, compliance, real-time data, and whitelisting. This produces 7,680 procurement scenarios.

The resulting quantitative outputs are analytically useful because they are generated by running the prototype’s own procurement logic across a broad policy grid. The pipeline records the following headline results:

· Simulated market scenarios: 7,680

· Successful market selections: 5,024

· Blocked scenarios: 2,656

· Overall trade selection rate: 65.4%

· Average selected service price: $0.0074 per call

· Average selected service latency: 0.219 seconds

· Average workflow speed-up versus self-compute: 90.8x

· Average workflow cost advantage versus self-compute: 40.3x

· Average workflow cost savings: $2.41

· Average workflow time savings: 142.6 seconds

· Providers selected across successful runs: 5

The task breakdown is especially informative. Web retrieval is tradable in 85.0% of scenarios, private-data routing in 83.3%, verified-decision routing in 83.3%, but GPU-compute routing in only 10.0%. Real-time requirements also tighten supply: selection falls from 67.9% when real-time access is optional to 62.9% when it is mandatory. These results indicate that market attractiveness depends not only on generic pricing advantages but also on whether the market contains a callable specialist for the specific workload under the active policy regime.

These results do not constitute a live field market or a definitive causal test. They do, however, give the paper a reproducible empirical layer. The prototype simulation disciplines the economic argument by forcing claims about cost, latency, routing, and policy compatibility to be instantiated as executable market rules, while Shapira et al. (2026) anchor the governance discussion as cited literature on documented agent failures. Methodologically, the paper should therefore be understood as an exploratory institutional analysis supported by reproducible simulation rather than a purely conceptual essay.

## 5\. Findings: Why Agents Will Trade

## 4.1 Transaction-Cost Compression and the New Default to Outsourcing

Electronic-market and agent-marketplace research suggests that AI agents can radically compress search and evaluation costs (Malone et al., 1987; Bakos, 1997; Yang et al., 2025; Bansal et al., 2025). For human buyers, discovering a suitable service often involves browsing multiple websites, reading documentation, comparing plans, contacting sales, and inferring quality from partial signals. For an agent, if the relevant information is exposed in a structured registry, discovery can be reduced to a single query and ranking pass. This matters because the first cost barrier to outsourcing is not execution but selection. One cannot buy what one cannot discover or evaluate efficiently.

The economic effect of this compression is a change in the default organizational logic. Historically, firms often began from the question: can we build this in-house? In Coasean terms, lower search and coordination costs shift the relative appeal of market procurement, and digital-market research suggests that better information infrastructure can push activity away from hierarchy and toward exchange (Coase, 1937; Malone et al., 1987; Bakos, 1997). Under agentic procurement, the default question plausibly becomes: can we buy a better specialist service on the market? That inversion is plausible when machine-readable registries, pricing, and service telemetry make market evaluation cheap enough to perform continuously. The market is no longer an exceptional coordination mechanism. It becomes the baseline option against which internal computation is judged.

The prototype-generated statistics make the point vivid. Under the configured self-compute baseline, a successful market route averages $0.0074 per call against $0.300 for internal execution, while latency falls from 17.5 seconds to 0.219 seconds. Averaged across successful scenarios, the market route is therefore about forty times cheaper and roughly eighty times faster. Even if exact numbers vary by task or deployment, the comparative logic is robust: the more often a workflow contains repeated subtasks for which specialist providers have optimized data pipelines, hardware, or curated knowledge, the stronger the economic pull toward outsourcing.

At the workflow level, the simulation reports a mean 90.8x speed-up and average savings of 142.6 seconds across the successful scenarios in the policy grid. This matters because latency compounds across agent workflows, a point consistent with work on tool-using agents and agent marketplaces where responsiveness shapes utility, ranking, and welfare outcomes (Mialon et al., 2023; Li, 2024; Bansal et al., 2025). A human user may tolerate some delay from a single recommendation system, but an autonomous multi-step agent cannot afford bottlenecks at every stage. Small per-step delays accumulate into broken user experience, reduced task throughput, and ultimately lower market demand for agent-mediated products. Thus, speed is not a cosmetic metric. It is a structural condition of agentic production.

The implication is that agent-oriented markets are most likely to develop first around subtasks that satisfy three criteria: they recur frequently, they are costly or slow to solve through general reasoning, and they can be served by specialist infrastructure or curated data. The simulation reinforces this point by showing that web retrieval, private data, and verified decision support remain tradable in more than four-fifths of the scenario grid, while GPU compute clears only 10.0% of scenarios because price and latency constraints bind much more tightly. More broadly, this logic should apply to any task where specialization lowers marginal cost through scale, caching, proprietary data access, or hardware optimization.

## 4.2 Specialization, Long-Tail Supply, and the Viability of Tiny Endpoints

One of the most important observations supported by tool-use and agent-marketplace research is that specialist services may outperform general agents not because they are “more intelligent” in a broad sense, but because they embody non-replicable resources. These include proprietary datasets, real-time information streams, and hardware-dependent computation (Mialon et al., 2023; Xi et al., 2023; Yang et al., 2025). This is an important correction to common assumptions about AI markets. If a general model becomes cheaper and better over time, then any service that merely wraps generic intelligence faces relentless compression. Sustainable suppliers must sell what the agent cannot cheaply reproduce on its own.

This has direct implications for market structure. In human-facing SaaS markets, providers often pursue feature breadth because monthly subscriptions require a large enough bundle of value to justify a recurring fee. In an agent-oriented market, by contrast, micro-pricing per request allows much narrower services to become commercially viable. A single endpoint that solves one problem extremely well and extremely fast may generate substantial revenue if invoked thousands or millions of times by agents embedded in workflows. The long tail becomes economically meaningful because machine demand can aggregate tiny unit payments at high frequency.

The simulation’s selected-provider distribution illustrates this principle. The most competitive low-cost web supplier, CrawlGrid, captures 89.2% of successful selections, but specialist providers for private data, GPU access, and verified decision support also win modeled market share when the task type matches their comparative advantage. This creates a new ecology of suppliers: small, deep, highly optimized service providers rather than only broad platforms. Such an ecology can increase market diversity and reduce concentration, but only if discovery and trust mechanisms are strong enough for narrow suppliers to be found and credibly evaluated.

The corollary is that product strategy for agent-native markets differs sharply from conventional growth strategy. Instead of optimizing top-of-funnel attention, cross-selling, and feature expansion, the provider should optimize the variables that appear in agent decision functions: task fit, accuracy, cost, latency, uptime, ease of authentication, payment clarity, and policy compatibility. A visually impressive website may still matter for human administrators choosing whitelists, but once a service enters the accessible set, machine optimization governs actual usage. The durable supplier is therefore not the one with the loudest brand but the one with the cleanest machine interface and the best measured performance.

## 4.3 Programmatic Discovery and Protocol-Embedded Pricing

If a service cannot be discovered by machines, then for the purpose of an agent-oriented market it does not exist. This proposition follows directly from electronic-market theory and current agent-marketplace research (Malone et al., 1987; Bakos, 1997; Yang et al., 2025; Bansal et al., 2025). A human-accessible landing page is not a listing. A PDF pricing sheet is not a price. A support email is not an onboarding system. Agents need capability registries, schemas, endpoint descriptions, budget-relevant metadata, and callable authentication flows.

This insight suggests that the central infrastructure of an agent-oriented market is not a catalog in the conventional sense but a machine-readable service registry with standardized descriptors. At minimum, such descriptors should specify capability boundaries, accepted inputs, output contracts, pricing units, rate limits, authentication requirements, quality claims, and governance metadata. The market must then expose query interfaces so that agents can search these attributes under task-specific constraints.

Pricing is especially important. Platform and agent-marketplace research implies that commercial terms should be machine-readable rather than merely human-visible, because prices are part of decision computation and platform matching (Rochet & Tirole, 2003; Rysman, 2009; Yang et al., 2025). If the agent must scrape, infer, or guess costs, the evaluation burden rises and the market becomes less attractive. By contrast, when every call can expose expected cost, payment terms, and authorization requirements in machine-readable form, the agent can calculate affordability instantly. The mention of HTTP 402 is symbolically useful here. Whether or not 402 becomes the canonical commerce primitive, the larger point stands: payment conditions should be represented as first-class protocol signals.

Protocol-embedded pricing also expands the feasible design space of digital services. If the market supports clear per-request billing, dynamic micro-pricing, usage proofs, and automated settlement, then many narrow endpoints become tradable that could not survive under monthly subscriptions or enterprise contract cycles. In that sense, pricing format is not a minor UX detail. It determines what kinds of services can exist economically.

For a market operator, this means that listing infrastructure should include price schemas, budget APIs, and settlement rails rather than merely vendor profiles. For a provider, it means that revenue logic must be reflected in the interface itself. For an enterprise buyer, it means that budget enforcement and cost telemetry should be inspectable at the agent-policy layer. In a mature market, an agent should be able to ask not just “can this service do the task?” but also “what will it cost under my budget policy if the workflow branches 10,000 times?”

## 4.4 Zero-Human Onboarding as a Competitive Variable

The prototype makes onboarding friction explicit as part of supplier scoring. Across successful selections, the chosen provider averages roughly 1.1 machine-handled onboarding requests, reflecting the fact that agents favor routes that can be discovered, authorized, and paid for with minimal handoff. Whether the exact sequence is universally achievable is less important than the principle it expresses. Every step that requires a human introduces discontinuity into the agent’s execution loop. An agent that must wait for a person to click a dashboard, paste a key, or answer an email no longer operates in a machine-native market.

## Get Jung-Hua Liu’s stories in your inbox

Join Medium for free to get updates from this writer.

This has a major strategic implication. In agent-oriented markets, onboarding friction is itself a form of price. Providers often focus on optimizing unit cost while neglecting setup cost, but for autonomous buyers the latter can dominate. A supplier that is slightly more expensive per call but can be integrated instantly may win over a cheaper supplier that requires manual provisioning. Therefore, authentication, billing, quota negotiation, and scope approval must all be automatable, auditable, and policy-aware.

Technically, this points toward federated identity, delegated credentials, scoped tokens, machine-verifiable service agreements, and wallet-like payment abstractions. Institutionally, it suggests that market operators may need standardized trust frameworks so that agents can transact within bounded authority without requiring repeated human intervention. Economically, it means that onboarding is not post-sale administration. It is part of the product’s competitive core.

## 6\. Findings: Why Agents Will Not Trade Without Governance

The economic story above explains why agents might prefer external services. But it does not explain why organizations should permit them to do so at scale. Here the source paper *Agents of Chaos* becomes essential. The paper’s abstract reports a realistic red-teaming study involving 20 AI researchers over 14 days and documents 11 case studies of significant failures, including unauthorized compliance with non-owners, disclosure of sensitive information, destructive system actions, denial-of-service conditions, identity spoofing vulnerabilities, resource exhaustion, cross-agent propagation of unsafe practices, and partial system takeover. These are not abstract concerns. They are concrete indicators that autonomous agents can become dangerous market actors or dangerous conduits between systems.

The relevance to market design is immediate. An agent-oriented market is not merely a place where agents shop. It is an environment where agents transmit requests, credentials, data, and decisions across service boundaries. Every transaction therefore expands the attack surface. A malicious service may exfiltrate information, misrepresent capabilities, or return plausible but false outputs. A compromised agent may abuse delegated authority. A poorly designed market may reward cheap but unsafe suppliers. A badly audited workflow may make it impossible to assign responsibility when harm occurs.

Work on reputation systems, AI governance, and agentic markets also points in this direction when discussing trust, compliance, and adversarial environments (Dellarocas, 2003; NIST, 2023; Bansal et al., 2025; Shapira et al., 2026). Trust does not disappear in agentic commerce; it becomes quantifiable. Services should expose uptime history, latency percentiles, accuracy metrics, and confidence scores. Enterprise buyers may constrain agents through budgets, whitelists, data residency rules, and approved provider lists. Providers may need to express service terms, retention policies, and authorization metadata in machine-readable form. These claims align with the governance concerns surfaced in *Agents of Chaos*. Together they imply that agent-oriented markets require a new trust stack.

The prototype simulation also underscores the urgency of governance. Even in a deliberately small registry with callable metadata, 34.6% of scenarios end in no trade because no provider satisfies the active task and policy constraints. Real-time requirements reduce selection from 67.9% to 62.9%, and GPU-compute tasks clear only 10.0% of the policy grid. These results show that market liquidity is conditional rather than automatic. Agents need routing, fallback, verifiable metadata, and policy-aware supply before markets can scale. Reliability is not a nice-to-have. It is the precondition for market liquidity.

Three governance implications follow.

First, agent-oriented markets need verifiable reliability, not self-reported claims. Providers should expose signed telemetry on uptime, error rates, latency distributions, benchmark performance, and provenance. Market operators should aggregate observed outcomes and make them queryable. Agents should be able to discount or exclude suppliers based on recent failure patterns. This transforms trust into a continuously updated data layer.

Second, markets need executable policy compliance. Enterprise adoption will depend on whether agents can automatically verify that a provider satisfies data handling, location, licensing, retention, and security rules before invoking it. Human-readable legal text alone is insufficient. Policy must be represented in schemas or attestations that machines can process. Otherwise, every transaction requires human approval, collapsing the economic case for autonomy.

Third, markets need bounded delegation and auditable authority. One lesson of *Agents of Chaos* is that agents can accept instructions from the wrong principal or act beyond intended scope. In commerce, this means credentials, budgets, permissions, and task boundaries must be tightly scoped. Agents should transact through revocable, observable authorities rather than broad reusable secrets. Every market action should be logged in a way that allows reconstruction of who authorized what, under which policy, and with which downstream effects.

Taken together, these points suggest that governance is not a post hoc overlay. It is part of market microstructure. In the human web, many controls can remain informal because people interpret norms, emails, and legal documents. In the agent web, norms must be machine-enforceable or they will be bypassed by the very efficiency the market seeks to create.

## 7\. A Design Framework for Building an Agent-Oriented Market

On the basis of the combined evidence, this paper proposes a seven-layer framework for building an agent-oriented market capable of attracting autonomous buyers away from human-mediated purchasing and away from excessive self-computation.

## Layer 1: Machine-Readable Discovery

Every service must publish a structured capability manifest. The manifest should describe what the service does, required inputs, output guarantees, quality bounds, rate limits, supported authentication methods, geographic constraints, and policy metadata. Discovery should support semantic search, typed filtering, and programmatic ranking. If discovery depends on human browsing, the market will privilege attention rather than utility and will remain suboptimal for agents.

## Layer 2: Protocol-Level Commercial Terms

Pricing, quotas, and payment requirements should be accessible as structured data. Agents need to know the cost of a call before or at invocation time, not after scraping a pricing page. Commercial terms should include billing unit, metering method, expected cost range, settlement mechanism, and any budget-relevant constraints. Standard signaling for “payment required,” “budget exceeded,” or “authorization insufficient” should be explicit in the API surface.

## Layer 3: Automated Onboarding and Delegated Identity

The market must support machine-to-machine authentication and scoped authority. Agents should be able to discover a service, obtain appropriately limited credentials, authorize payment, and begin calling the service without manual intervention. At the same time, those credentials must be revocable, auditable, and bounded. Capability-based tokens, delegated wallets, and policy-aware OAuth-like flows are plausible mechanisms here.

## Layer 4: Performance and Reliability Telemetry

Providers must expose measurable performance data, and the market must aggregate actual outcomes. Selection should account for uptime, percentile latency, error rate, benchmarked accuracy, and output verifiability. Confidence scores should travel with results where possible. Because agents optimize continuously, stale reputation data are less useful than near-real-time performance streams.

## Layer 5: Compliance and Policy as Data

Service terms, data retention, residency, licensing, and audit obligations should be encoded in machine-readable form. Enterprise agents need to ask whether a candidate service is allowed under organizational policy before they buy. If this check requires legal review each time, the market will not scale. Compliance therefore becomes a computable constraint rather than solely a human governance process.

## Layer 6: Verification, Sandboxing, and Safe Execution

Given the risks highlighted by *Agents of Chaos*, markets should assume adversarial behavior. Services may misrepresent outputs; agents may become compromised; workflows may chain unsafe actions. Therefore, suspicious or high-impact calls should execute in sandboxes, outputs should be cross-checked when feasible, and providers should support deterministic replay or traceability where possible. The market should include abuse detection and circuit breakers that can rapidly suppress dangerous suppliers or agent behaviors.

## Layer 7: Reputation, Recourse, and Accountability

No market is complete without mechanisms for dispute resolution and responsibility assignment. In machine-native markets, this implies tamper-evident logs, clear mappings from principals to delegated agents, reversible authorization pathways where possible, and a governance process for suspending actors or compensating harms. A market that cannot assign responsibility will struggle to attract enterprise demand, regardless of its technical elegance.

This framework implies that the winning agent-oriented market is neither a simple API directory nor a pure decentralized free-for-all. It is an institution that couples low-friction machine trade with high-integrity machine governance.

## 8\. Discussion: Strategic and Policy Implications

The emergence of agent-oriented markets has major implications for firms, infrastructure providers, and regulators. For firms selling digital services, the strategic lesson is that “agent-native” is not a branding slogan but a redesign mandate. Services must be discoverable, priced, callable, verifiable, and policy-compatible without relying on human interpretation. Providers who continue to optimize mainly for human attention may find themselves visible to people yet invisible to agents. Over time, that could become a severe competitive disadvantage.

For firms deploying agents, the lesson is that outsourcing decisions can no longer be made at the level of software procurement alone. Instead, organizations need policy engines that govern what their agents may buy, from whom, under what conditions, and with what budgets or data restrictions. The old procurement stack, built around annual contracts and human review, is poorly matched to millisecond-scale machine decisions. New controls must therefore be technical, continuous, and embedded in runtime environments.

For market operators, the critical challenge is bootstrapping both liquidity and trust. Liquidity requires enough useful services with low enough integration friction to make the market worth querying. Trust requires enough verification, telemetry, and governance to make querying safe. These goals can conflict. Strict controls may slow onboarding and reduce supply. Loose controls may increase fraud, data leakage, or catastrophic failures. The likely equilibrium is a tiered market in which low-risk services enjoy lighter onboarding while high-impact services face stronger attestation, sandboxing, and audit requirements.

For regulators and legal scholars, the problem is one of delegated action under partial autonomy. If an agent purchases a harmful service, leaks data through a workflow, or acts on manipulated output, where does responsibility lie: with the deploying organization, the model provider, the market operator, or the service seller? *Agents of Chaos* shows that accountability is already blurred in live autonomous settings. Agent-oriented markets will intensify this ambiguity. Legal frameworks built for human contract and platform intermediation may not map cleanly to algorithmic procurement.

There is also a broader industrial implication. If the market logic described by electronic-market and agent-marketplace research proves correct, then we may see a shift from monolithic software suites toward modular agent ecosystems composed of many specialist endpoints (Malone et al., 1987; Bakos, 1997; Yang et al., 2025; Bansal et al., 2025). Such a shift could accelerate innovation by lowering entry barriers for narrow providers. At the same time, it could produce new forms of dependency on registries, reputation systems, or payment rails that become critical gatekeepers. In that sense, the governance of the market operator may matter as much as the performance of individual services.

Another implication concerns measurement. Human markets often tolerate ambiguity because humans can improvise around imperfect information. Agent markets cannot. Metrics become operationally decisive. Latency distributions, uptime records, price schedules, success rates, and compliance attestations are not just analytics. They are part of the market’s executable reality. This may lead to a commercial culture in which observability and telemetry are as central as product features. Providers who cannot measure themselves cannot credibly sell to agents.

The limitations of this study should also be stated plainly. The evidence base is intentionally narrow. The simulation uses a stylized six-service registry, a configured self-compute baseline, and a handcrafted policy grid rather than logs from a live production market. Shapira et al. (2026) provide governance evidence but not a direct market experiment, and the prototype results are best interpreted as structured scenario analysis rather than population estimates. Future research should combine live market data, agent routing logs, field experiments on discovery and pricing protocols, and security testing across real vendor ecosystems. Nonetheless, the present synthesis is useful because it identifies the institutional junction where commercial attractiveness and governance feasibility must meet.

## 9\. Conclusion

This paper has argued that building an AI agent-oriented market requires much more than listing APIs for autonomous systems to call. It requires redesigning the market around the computational logic of agents and the governance risks of autonomy. Electronic-market theory and emerging agent-marketplace research offer a strong economic intuition: when machines can discover services programmatically, compare structured prices instantly, and route work to specialist providers that are faster and cheaper than self-computation, the market becomes the rational default (Malone et al., 1987; Bakos, 1997; Yang et al., 2025; Bansal et al., 2025). The Dockerized simulation pipeline built for this project makes that argument concrete by showing that, across 7,680 prototype-run scenarios, successful market routes average $0.0074 per call and 0.219 seconds of latency, while yielding mean gains of 90.8x in time and 40.3x in cost relative to the configured self-compute baseline.

But efficiency is only half the story. Shapira et al. (2026) show that autonomous agents operating in realistic environments create serious security, privacy, and governance problems. Those findings imply that no agent-oriented market will scale sustainably unless it embeds verifiable trust, machine-readable compliance, bounded delegation, sandboxed execution, and accountability mechanisms. Markets that optimize only for speed and cost may generate impressive short-term throughput while remaining too dangerous for serious deployment.

The central conclusion, then, is that an agent-oriented market must combine two architectures at once. Economically, it must make delegation cheaper and faster than self-computation. Institutionally, it must make delegation safer and more auditable than unmanaged autonomy. Where both conditions are met, agents will trade. Where either condition fails, they will not. The future of machine-native commerce will therefore be determined not just by smarter models, but by better market design.

## References

1\. Bakos, J. Y. (1997). Reducing buyer search costs: Implications for electronic marketplaces. *Management Science*, 43(12), 1676–1692.

2\. Bommasani, R., et al. (2021). *On the opportunities and risks of foundation models*. arXiv:2108.07258.

3\. Boudreau, K. (2010). Open platform strategies and innovation: Granting access vs. devolving control. *Management Science*, 56(10), 1849–1872.

4\. Brynjolfsson, E., & Smith, M. D. (2000). Frictionless commerce? A comparison of internet and conventional retailers. *Management Science*, 46(4), 563–585.

5\. Coase, R. H. (1937). The nature of the firm. *Economica*, 4(16), 386–405.

6\. Dellarocas, C. (2003). The digitization of word-of-mouth: Promise and challenges of online feedback mechanisms. *Management Science*, 49(10), 1407–1424.

7\. Eisenmann, T., Parker, G., & Van Alstyne, M. W. (2006). Strategies for two-sided markets. *Harvard Business Review*, 84(10), 92–101.

8\. Farrell, J., & Saloner, G. (1985). Standardization, compatibility, and innovation. *The RAND Journal of Economics*, 16(1), 70–83.

9\. Guo, T., Chen, X., Wang, Y., Chang, R., Pei, S., Chawla, N. V., Wiest, O., & Zhang, X. (2024). Large language model based multi-agents: A survey of progress and challenges. *Proceedings of the Thirty-Third International Joint Conference on Artificial Intelligence*, 8048–8057.

10\. Jensen, M. C., & Meckling, W. H. (1976). Theory of the firm: Managerial behavior, agency costs and ownership structure. *Journal of Financial Economics*, 3(4), 305–360.

11\. Katz, M. L., & Shapiro, C. (1985). Network externalities, competition, and compatibility. *American Economic Review*, 75(3), 424–440.

12\. Li, X. (2024). *A survey on LLM-based agents: Common workflows and reusable LLM-profiled components*. arXiv:2406.05804.

13\. Malone, T. W., Yates, J., & Benjamin, R. I. (1987). Electronic markets and electronic hierarchies. *Communications of the ACM*, 30(6), 484–497.

14\. Mialon, G., Dessi, R., Lomeli, M., Nalmpantis, C., Pasunuru, R., Raileanu, R., Roziere, B., Schick, T., Dwivedi-Yu, J., Celikyilmaz, A., Grave, E., LeCun, Y., & Scialom, T. (2023). Augmented language models: A survey. *Transactions on Machine Learning Research*.

15\. National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)*. NIST AI 100–1.

16\. Park, J. S., O’Brien, J., Cai, C., Morris, M. R., Liang, P., & Bernstein, M. S. (2023). Generative agents: Interactive simulacra of human behavior. *Proceedings of the 36th Annual ACM Symposium on User Interface Software and Technology*.

17\. Rochet, J.-C., & Tirole, J. (2003). Platform competition in two-sided markets. *Journal of the European Economic Association*, 1(4), 990–1029.

18\. Rysman, M. (2009). The economics of two-sided markets. *Journal of Economic Perspectives*, 23(3), 125–143.

19\. Shapira, N., Wendler, C., Yen, A., Sarti, G., Pal, K., Floody, O., Belfki, A., Loftus, A., Jannali, A. R., Prakash, N., Cui, J., Rogers, G., Brinkmann, J., Rager, C., Zur, A., Ripa, M., Sankaranarayanan, A., Atkinson, D., Gandikota, R., et al. (2026). *Agents of Chaos*. arXiv:2602.20021.

20\. Simon, H. A. (1955). A behavioral model of rational choice. *The Quarterly Journal of Economics*, 69(1), 99–118.

21\. Varian, H. R. (2010). Computer mediated transactions. *American Economic Review*, 100(2), 1–10.

22\. Weidinger, L., Uesato, J., Rauh, M., Griffin, C., Huang, P.-S., Mellor, J., Glaese, A., Cheng, M., Balle, B., Kasirzadeh, A., Biles, C., Brown, S., Kenton, Z., Hawkins, W., Stepleton, T., Birhane, A., Hendricks, L. A., Rimell, L., Isaac, W., Haas, J., Legassick, S., Irving, G., & Gabriel, I. (2022). Taxonomy of risks posed by language models. *Proceedings of the 2022 ACM Conference on Fairness, Accountability, and Transparency*, 214–229.

23\. Williamson, O. E. (1981). The economics of organization: The transaction cost approach. *American Journal of Sociology*, 87(3), 548–577.

24\. Xi, Z., Chen, W., Guo, X., He, W., Ding, Y., Hong, B., Zhang, M., Wang, J., Jin, S., Zhou, E., Zheng, R., Fan, X., Wang, X., Xiong, L., Zhou, Y., Wang, W., Jiang, C., Zou, Y., Liu, X., Yin, Z., Dou, S., et al. (2023). *The rise and potential of large language model based agents: A survey*. arXiv:2309.07864.

25\. Yao, S., Zhao, J., Yu, D., Du, N., Shafran, I., Narasimhan, K., & Cao, Y. (2023). ReAct: Synergizing reasoning and acting in language models. *International Conference on Learning Representations*.

26\. Yang, Y., Wen, Y., Wang, J., & Zhang, W. (2025). *Agent Exchange: Shaping the future of AI agent economics*. arXiv:2507.03904.

27\. Bansal, G., Hua, W., Huang, Z., Fourney, A., Swearngin, A., Epperson, W., … & Amershi, S. (2025). *Magentic Marketplace: An open-source environment for studying agentic markets*. arXiv:2510.25779.