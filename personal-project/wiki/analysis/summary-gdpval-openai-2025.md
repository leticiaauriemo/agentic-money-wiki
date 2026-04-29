---
title: "Summary: GDPval — Evaluating AI on Economically Valuable Tasks (OpenAI, 2025)"
type: summary
topic: personal-project
source_type: academic
tags: [evaluation, economic-value, occupations, benchmark, frontier-models, labor, GDP]
sources: [gdpval-openai-2025.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Summary: GDPval — Evaluating AI on Economically Valuable Tasks (OpenAI, 2025)

**Authors:** Tejal Patwardhan, Rachel Dias, Elizabeth Proehl, Grace Kim, Michele Wang, Olivia Watkins, Simón Posada Fishman, Marwan Aljubeh, Phoebe Thacker, Laurance Fauconnet, Natalie S. Kim, Patrick Chao, Samuel Miserendino, Gildas Chabot, Jerry Tworek, David Li, Michael Sharman, Alexandra Barr, Amelia Glaese (OpenAI)

**Source:** `gdpval-openai-2025.pdf` | arXiv:2510.05374

**Answers:** *How capable are frontier AI models at real-world economically valuable tasks, and which occupations are most affected?*

---

## What is GDPval

A benchmark evaluating AI model performance on **real-world economically valuable tasks** — not academic-style reasoning tests. Coverage:
- **9 sectors** contributing over 5% to U.S. GDP
- **44 occupations** earning $3T annually
- **1,320 tasks** (full set) / 220 tasks (gold subset, open-sourced)
- Tasks created by industry professionals averaging **14 years of experience**
- Tasks require an average of **7 hours of expert work** to complete (some span weeks)

Primary metric: head-to-head comparison against human expert baseline (win rate), not accuracy on a fixed answer.

---

## Key findings

**Frontier model performance is improving roughly linearly over time.** Current best frontier models are approaching industry expert quality on GDPval.

**Frontier models can perform tasks cheaper and faster than experts when paired with human oversight.** The analysis specifically examines AI + human oversight rather than fully autonomous completion.

**Reasoning effort matters but has diminishing returns.** Increased reasoning effort improves performance on GDPval, but the gains aren't always linear.

**Tasks requiring up to 7 expert hours with average difficulty.** This establishes that the tasks are genuinely representative of professional knowledge work, not toy problems.

---

## Occupations covered

Representative sectors: professional services (consulting, legal, financial), healthcare, technology, manufacturing, media. The benchmark deliberately targets occupations that are "predominantly digital" — where at least 60% of component tasks are digital (using O*NET classifications).

Notably, the professionals whose work products were sourced include former employees from: Goldman Sachs, McKinsey-adjacent firms (Accenture, PwC), law firms (Paul Weiss, White & Case), Morgan Stanley, Bloomberg, JPMorgan Chase, and dozens of other enterprise-tier organizations.

---

## Key quotes

> "Frontier model performance on GDPval is improving roughly linearly over time, and the current best frontier models are approaching industry experts in deliverable quality." (Abstract)

> "Tasks require an average of 7 hours of work for an expert professional to complete. On the high end, tasks span up to multiple weeks of work." (Section 2.3)

---

## Relevance to thesis

1. **The wedge is in the right place.** GDPval confirms that frontier models are approaching expert performance on professional knowledge work tasks — which means the demand for AI-assisted professional work is real and growing. The startup's target customers (management consultants, policy researchers) are in exactly the sectors GDPval covers.

2. **"Approaching" ≠ "replacing."** The caveat "when paired with human oversight" and the win rate framing suggest frontier models are powerful augmentation tools, not drop-in replacements. This is where specialists with proprietary data access and domain optimization add residual value — they bridge the gap between "approaching expert quality" and "certified expert output."

3. **7-hour tasks are the target.** GDPval's emphasis on multi-hour, multi-week tasks validates the memory wall framing — these are exactly the tasks that break single-agent approaches and require orchestrated multi-agent execution. The startup targets this exact segment.

---

## Related pages

[[memory-wall]]
[[overview]]
[[the-five-problems]]

## Source

- [[gdpval-openai-2025]] (Patwardhan, Dias et al., OpenAI, 2025)
