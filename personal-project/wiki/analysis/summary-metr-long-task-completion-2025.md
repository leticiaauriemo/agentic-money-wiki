---
title: "Summary: Measuring AI Ability to Complete Long Software Tasks (Kwa et al., 2025)"
type: summary
topic: personal-project
source_type: academic
tags: [evaluation, time-horizon, long-tasks, frontier-models, capability-forecasting, reliability]
sources: [metr-long-task-completion-2025.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Summary: Measuring AI Ability to Complete Long Software Tasks (Kwa et al., 2025)

**Authors:** Thomas Kwa, Ben West, Joel Becker, Amy Deng, Katharyn Garcia, Max Hasin, Sami Jawhar, Megan Kinniment, Nate Rush, Sydney Von Arx, and others (Model Evaluation & Threat Research — METR)

**Source:** `metr-long-task-completion-2025.pdf` | arXiv:2503.14499

**Answers:** *How long of a task can current AI agents reliably complete, and how fast is this capability growing?*

---

## Core metric: 50% task-completion time horizon

The paper proposes a new metric: **50%-task-completion time horizon** — the time humans typically take to complete tasks that AI models can complete with 50% success rate. This provides an intuitive, quantitative comparison between AI and human capabilities.

Key insight: instead of asking "what percentage of benchmark X does the model pass?", ask "what length task (in human-equivalent minutes/hours) can the model complete reliably?"

---

## Main findings

**Current frontier models (as of study): ~110 minute time horizon at 50% success.** Models like o3 can reliably complete tasks that take a skilled human about 110 minutes, half the time.

**Time horizon has been doubling approximately every 7 months since 2019.** An exponential trend on log-linear scale. Notably: the rate may have **accelerated since 2024**.

**At the 80% success threshold, horizons are ~5x shorter.** High reliability requires much shorter tasks than the 50% threshold.

**Performance is lower on less-structured, "messier" tasks.** The trend is clearest on software engineering benchmarks; messier real-world tasks show more noise.

---

## What drives capability improvement

The paper identifies four primary drivers:
1. **Improved logical reasoning** — models make fewer cascading errors in multi-step reasoning
2. **Better tool use** — more reliable invocation and integration of external tools
3. **Greater reliability** — reduced variance in whether the model completes vs. fails or loops
4. **Better self-awareness** — models better recognize when they're stuck and adapt

---

## Forecast

Naively extrapolating the doubling-every-7-months trend: **AI will reach a >1 month time horizon (167 work hours) between mid-2028 and mid-2031.** This would mean AI can independently complete many software tasks currently requiring months of human work.

The paper explicitly notes this extrapolation has large uncertainty bands and external validity concerns.

---

## Key quotes

> "The length of tasks (measured by how long they take human professionals) that generalist autonomous frontier model agents can complete with 50% reliability has been doubling approximately every 7 months for the last 6 years." (Abstract)

> "Within 5 years, AI systems will be capable of automating many software tasks that currently take humans a month." (Abstract)

---

## Relevance to thesis

1. **The memory wall is the bottleneck.** The 110-minute current horizon and slow improvement at 80% threshold confirms that task length — not reasoning ability — is the binding constraint on agent reliability. This is exactly the memory wall. The startup's decomposition architecture breaks multi-hour enterprise tasks into subtasks within the reliable range.

2. **The window for this business is limited but long enough.** If the 7-month doubling holds, a 110-minute horizon today becomes an 8-hour horizon in ~2.5 years. The startup has several years where orchestration and trust infrastructure creates value before raw model capability closes the gap on medium-length tasks. But the moat must compound faster than model capability improves — which is why per-client context and verified specialist networks matter.

3. **Faster improvement since 2024.** If the trend is accelerating, the strategic window may be shorter than the trend line suggests. This is the strongest argument for moving fast: the window where orchestration adds value over raw frontier models may compress.

---

## Related pages

[[memory-wall]]
[[the-five-problems]]
[[open-questions]]
[[overview]]

## Source

- [[metr-long-task-completion-2025]] (Kwa, West, Becker et al., METR, 2025)
