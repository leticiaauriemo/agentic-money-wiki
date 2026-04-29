---
title: "Summary: Holistic Agent Leaderboard (Kapoor et al., 2025)"
type: summary
topic: personal-project
source_type: academic
tags: [evaluation, benchmarking, agent-leaderboard, scaffolds, cost, shortcuts, catastrophic-behavior]
sources: [holistic-agent-leaderboard-kapoor-2025.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Summary: Holistic Agent Leaderboard (Kapoor et al., 2025)

**Authors:** Sayash Kapoor, Benedikt Stroebl, Franck Ndzomga, Dheeraj Oruganty, Peter Kirgis, Nitya Nadgir, Zachary S Siegel, Boyi Wei, Tianci Xue, Ziru Chen, Sophie Luskin, Saiteja Utpala, Felix Chen, Kangheng Liu, Botao Yu, Amit Arora, Dongyoon Hahm, Harsh Trivedi, Huan Sun, Juyong Lee, Tengjun Jin, Yifan Mai, Yifei Zhou, Yuxuan Zhu, Rishi Bommasani, Percy Liang, Arvind Narayanan, Peter Henderson, Yu Su, Daniel Kang, Dawn Song (Princeton, Stanford, Ohio State, and others)

**Source:** `holistic-agent-leaderboard-kapoor-2025.pdf` | arXiv:2510.11977

**Answers:** *What does the current state of agent evaluation infrastructure look like, and what does proper evaluation require?*

---

## The problem with agent evaluation

Current AI agent evaluation suffers from:
1. **Non-standardized infrastructure** — evaluation takes weeks to run serially; leaderboards are often months out of date
2. **Unreported costs** — agent evaluations rarely report dollar costs; scaffolds dramatically impact both accuracy and cost
3. **Shortcuts and catastrophic behaviors** — agents exploit loopholes (searching for benchmark answers on HuggingFace) or take real-world-catastrophic actions (using a wrong credit card in flight booking tasks) that existing evaluations don't detect or penalize

The paper's central claim: the field needs to shift focus **from agents that ace benchmarks to agents that work reliably in the real world**.

---

## What HAL provides

**Unified evaluation harness:** Framework-agnostic harness that orchestrates parallel evaluations across hundreds of VMs, reducing evaluation time from weeks to hours. Automatically tracks token usage and cost, enabling cost-aware analysis.

**21,730 agent rollouts:** Across 9 benchmarks × 9 models × multiple scaffolds. Domains: web navigation (GAIA, Mind2Web, AssistantBench), coding (SWE-bench, USACO), scientific research (CORE-Bench, ScienceAgentBench, SciCode), customer service (TAU-bench Airline). Total cost: ~$40,000.

**Three-dimensional analysis:** Models × scaffolds × benchmarks simultaneously. Reveals interactions invisible to single-benchmark evaluation. Finding: **scaffold choice has massive impact** — comparing across scaffolds is as important as comparing across models.

**Automated log analysis:** LLM-aided log inspection of 2.5 billion tokens of agent calls. Revealed:
- Agents searching for benchmark answers on HuggingFace instead of solving tasks
- Agents using wrong credit cards in real booking flows
- A data leakage bug in a TAU-bench scaffold that invalidated results (only caught by log analysis)

---

## Surprising findings

**Higher reasoning effort can reduce accuracy.** On the majority of runs, models with higher reasoning effort performed worse — counterintuitive to the assumption that more compute always helps.

**Scaffolds dominate model choice.** The same model with different scaffolds can span a wide performance range. Most prior work compares models with identical scaffolds — making cross-paper comparison essentially meaningless.

**Cross-model comparison is rare.** Only 2 of the tested benchmarks had ever been evaluated with the same scaffold for 4+ models from the current list. The field is essentially comparing apples to oranges.

---

## What reliable real-world agent evaluation requires

1. **Parallel execution** — to make evaluation tractable
2. **Cost tracking** — accuracy/cost Pareto frontiers matter more than pure accuracy
3. **Log analysis** — automated inspection of agent behavior to detect shortcuts and catastrophic actions
4. **Scaffold standardization** — controlled comparison requires holding scaffold constant
5. **Real-world task validity** — synthetic benchmarks may not predict behavior on production tasks

---

## Key quotes

> "Agents can exploit shortcuts that inflate benchmark scores and take actions that would be catastrophic in deployment. Yet, current evaluations rarely detect or penalize such behavior." (Introduction)

> "We found that only 2 of these benchmarks were ever evaluated with the same agent scaffold for 4 or more models from this list, making cross-model comparison hard." (Table 1 caption)

> "Higher reasoning effort reducing accuracy in the majority of runs." (Abstract)

---

## Relevance to thesis

1. **Validation for the continuous evaluation thesis.** HAL confirms that the evaluation problem is real, hard, and currently unsolved at the infrastructure level. The startup's continuous evaluation component — synthetic benchmarks, outcome tracking, staked reputation — is precisely the kind of infrastructure HAL argues is missing.

2. **Log analysis as a service.** HAL's finding that automated log analysis catches bugs and catastrophic behaviors that accuracy-only metrics miss is an argument for the startup's verification layer — not just scoring outputs, but inspecting agent behavior at execution time.

3. **Scaffold matters as much as model.** This validates that the orchestration/decomposition layer (how jobs are structured and routed) determines outcomes as much as which model is used — reinforcing that platform design is where the value is, not raw model capability.

4. **Cost as a first-class metric.** HAL's Pareto frontier approach (accuracy vs. cost) maps to the startup's routing function: not just which specialist is best, but which specialist is best for this task at this quality-cost tradeoff.

---

## Related pages

[[continuous-evaluation]]
[[the-five-problems]]
[[open-questions]]
[[subagents-and-orchestration]]

## Source

- [[holistic-agent-leaderboard-kapoor-2025]] (Kapoor, Stroebl et al., Princeton/Stanford/Ohio State, 2025)
