---
title: "The Five Problems"
type: concept
topic: personal-project
tags: [problem, framing, thesis]
sources: []
created: 2026-04-22
updated: 2026-04-22
---

# The Five Problems

The company addresses five interlocking problems that collapse into
one product.

## 1. Memory wall

Agents break on long jobs due to five failure modes:
- Context overflow mid-job
- Instruction dilution as context fills
- Error accumulation from cascading partial failures
- State loss on interruption
- Evaluation blindness (confidently wrong outputs going undetected)

Bigger context windows don't fix this — attention quality degrades,
cost scales with context length, and state still doesn't persist across
sessions. See [[memory-wall]] for detail.

## 2. Discovery

Three layers, none solved:
- **Existence** — does a specialist that can do X exist?
- **Capability** — what exactly does it do, with what limits?
- **Trust and quality** — is it reliable, safe to invoke on my data?

MCP standardizes communication. It doesn't solve trust or cross-org
scale. See [[discovery-problem]] for detail.

## 3. Trust and safety

Cross-organizational subcontracting requires:
- Sandboxed execution (specialists can't exfiltrate data)
- Data isolation (specialists see only what they need per subtask)
- In-platform communication (specialists can't contact clients off-channel)
- Verification (outputs checked before delivery)
- Attestation (clients get cryptographic receipts for sensitive work)

See [[sandboxed-execution]] and [[confidential-compute]].

## 4. Per-client context

What compounds over time:
- Preferred deliverable formats
- Standing constraints (jurisdiction, conflicts of interest, tone)
- Which specialists performed well for this client
- Which past outputs they accepted vs. quietly rejected
- Workflow patterns (reviews, approvals, escalations)

This is the moat. See [[client-context-moat]].

## 5. Continuous evaluation

Specialists compete on synthetic benchmarks and anonymized real jobs.
Performance feeds routing. Benchmarks become proprietary infrastructure.
Staked reputation creates selection pressure. See [[continuous-evaluation]].

## How they interlock

Memory wall solved by decomposition → decomposition requires discovery →
discovery without trust is useless → trust without accumulated context is
shallow → context without continuous evaluation goes stale.

The product exists in the middle of all five.

## Related pages

[[overview]] — top-level thesis
[[memory-wall]] — concept stub
[[discovery-problem]] — concept stub
[[sandboxed-execution]] — concept stub
[[client-context-moat]] — concept stub
[[continuous-evaluation]] — concept stub
