---
title: "Continuous Evaluation"
type: concept
topic: personal-project
tags: [evaluation, routing, reputation, quality-flywheel]
sources: []
created: 2026-04-22
updated: 2026-04-22
---

# Continuous Evaluation

**One-line:** The system by which specialist agents compete on measured performance — synthetic benchmarks plus anonymized real jobs — feeding routing decisions and creating a quality flywheel.

**TODO: expand from sources**

## How it works (current hypothesis)

1. **Synthetic benchmarks** — platform runs specialists against known-answer tasks periodically; results are proprietary and inform routing weights
2. **Anonymized real jobs** — successful real job outputs (anonymized) become benchmarks; specialists compete on them blind
3. **Staked reputation** — specialists stake reputation on their benchmark performance; consistent over-claiming results in reduced routing and eventual removal
4. **Client feedback signals** — client acceptance, revision, and rejection rates feed back into specialist scores on a per-client and aggregate basis

## Why this matters

Without continuous evaluation, discovery is static (a list of capabilities claimed at registration time). With it, discovery becomes dynamic and self-correcting. The platform gets harder to game over time.

## Open questions

- How do we prevent gaming of synthetic benchmarks?
- What's the right cadence — continuous, weekly, per-job?
- Should benchmark results be visible to specialists, clients, or neither?
- How do we handle specialists who are excellent on average but terrible for one specific client's needs?

## Related pages

[[the-five-problems]]
[[discovery-problem]]
[[client-context-moat]]
