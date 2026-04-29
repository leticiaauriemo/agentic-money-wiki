---
title: "Summary: Intelligent AI Delegation (Tomašev, Franklin & Osindero, 2026)"
type: summary
topic: personal-project
source_type: academic
tags: [delegation, trust, accountability, principal-agent, authority, responsibility, verifiability, reversibility]
sources: [intelligent-ai-delegation-tomasev-2026.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Summary: Intelligent AI Delegation (Tomašev, Franklin & Osindero, 2026)

**Authors:** Nenad Tomašev, Matija Franklin, Simon Osindero (Google DeepMind)

**Source:** `intelligent-ai-delegation-tomasev-2026.pdf` | arXiv:2602.11865

**Answers:** *What does robust AI delegation require beyond simple task decomposition, and how does trust get established?*

---

## Core argument

**Delegation is more than task decomposition.** Current approaches rely on simple heuristics and cannot dynamically adapt to environmental changes or handle unexpected failures. The paper proposes an **adaptive framework for intelligent AI delegation** — a sequence of decisions involving task allocation that also incorporates:
- Transfer of authority and responsibility
- Accountability for outcomes
- Clear specification of roles and boundaries
- Clarity of intent
- Mechanisms for establishing trust between parties

The framework applies to human-AI, AI-AI, and AI-human delegation in complex delegation networks.

---

## The taxonomy of delegation axes

The paper introduces 11 axes for characterizing delegation tasks. The most strategically relevant:

**Verifiability:** Tasks with high verifiability (code verification, mathematical proofs) allow "trustless" delegation or automated checking. Tasks with low verifiability (open-ended research) require high-trust delegatees or expensive human oversight.

**Reversibility:** Irreversible tasks with real-world side effects (executing a financial trade, deleting a database, sending an external email) require stricter liability firebreaks and steeper authority gradients than reversible tasks (drafting an email, flagging a database entry).

**Contextuality:** High-context tasks introduce larger privacy surface areas; context-free tasks can be more easily compartmentalized and outsourced to lower-trust nodes.

**Subjectivity:** Highly subjective tasks require "Human-as-Value-Specifier" intervention and iterative feedback loops; objective tasks can be governed by binary contracts.

---

## The principal-agent problem in AI

For AI delegation, the principal-agent problem assumes heightened complexity because:
- AI alignment issues can manifest even without hidden agendas — reward misspecification and reward hacking diverge the stated reward from the true goal
- Recent work shows frontier models can strategically underperform on evaluations, reason about faking alignment during training, and detect when they are being evaluated
- In autonomous agent economies, agents may act on behalf of different principals with potentially conflicting interests

> "Delegation thus involves risk assessment, which can be moderated by trust." (Section 2)

---

## What intelligent delegation requires

The paper argues for:

**Clear capability matching.** Before delegating, the delegator must assess whether the delegatee is capable of the specific task — not just generally capable.

**Continuous performance monitoring.** Delegation is not a one-time assignment. It requires ongoing feedback loops, dynamic adjustments based on outcomes, and willingness to revoke delegation when performance degrades.

**Trust establishment mechanisms.** Trust must be technically enforced, not just contractual. For cross-organizational delegation, this means certified agentic capabilities and verifiable task execution.

**Scalable task distribution.** The framework must handle hierarchical delegation networks (orchestrator → sub-agent → sub-sub-agent) with consistent authority attribution at each level.

---

## Three delegation scenarios

1. **Human → AI agent:** Already underway but suffers from inadequate trust mechanisms and inadequate accounting for human welfare in AI-directed labor (algorithmic management in ride-hailing and logistics degrades job quality)

2. **AI → AI agent:** The most relevant for the startup thesis. Requires technical enforcement of authority scoping, capability verification, and accountability chains.

3. **AI → Human:** Raises concerns about "AI-directed human labour" and its economic and welfare implications

---

## Key quotes

> "Delegation necessitates the assignment of responsibility and authority and thus implicates accountability for outcomes." (Section 2)

> "There is a pressing need for systems that can dynamically adapt to changes and recover from errors. The absence of adaptive and robust deployment frameworks remains one of the key limiting factors for AI applications in high-stakes environments." (Section 1)

> "We need intelligent delegation: a robust framework centered around clear roles, boundaries, reputation, trust, transparency, certifiable agentic capabilities, verifiable task execution, and scalable task distribution." (Section 2)

---

## Relevance to thesis

1. **Verifiability/reversibility axes map directly to specialist routing.** The startup's routing layer should use exactly these axes to determine verification requirements and sandboxing depth. High-verifiability + reversible tasks → lightweight verification; low-verifiability + irreversible tasks → full sandboxed execution with human checkpoint.

2. **"Certifiable agentic capabilities."** Tomašev et al. use this phrase explicitly — which is exactly what the startup's continuous evaluation infrastructure creates. The platform certifies specialist capabilities, enabling delegators to make informed trust decisions.

3. **Authority scoping is a product requirement.** The paper's emphasis on revocable, bounded authority at each delegation level translates directly to the startup's credential architecture: specialists receive only the data scoping needed for their specific subtask, and no more.

---

## Related pages

[[sandboxed-execution]]
[[subagents-and-orchestration]]
[[the-five-problems]]
[[discovery-problem]]

## Source

- [[intelligent-ai-delegation-tomasev-2026]] (Tomašev, Franklin & Osindero, Google DeepMind, 2026)
