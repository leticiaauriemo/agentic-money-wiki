---
title: "Three Gaps That Will Decide Which Banks Are Ready For Agentic Payments"
type: summary
topic: agentic-money
source_type: news
tags: [compliance, identity-kyc, infrastructure, bank-api, agentic-commerce]
sources: ["three-gaps-agentic-payments.md.md"]
created: 2026-04-25
updated: 2026-04-25
---

# Three Gaps That Will Decide Which Banks Are Ready For Agentic Payments

**Source:** [Forbes Technology Council, 2026-04-21](https://www.forbes.com/councils/forbestechcouncil/2026/04/21/three-gaps-that-will-decide-which-banks-are-ready-for-agentic-payments/)
**Author:** [[dimitar-dimitrov]] (founder, Accedia)

## Key argument

Visa, Mastercard, Stripe, Google, and PayPal all shipped agentic commerce frameworks within a six-month window in 2025. Banks are on the receiving end of those transactions and, architecturally, most are not ready. Every layer of existing infrastructure assumes a human is behind every transaction. Three specific gaps expose that assumption:

---

## Gap 1 — Fraud detection

Existing fraud models are trained on human behavior patterns. A legitimate AI agent and a malicious one look identical to them. Banks face a binary choice: tighten controls and block legitimate agent volume, or loosen them and accept greater fraud exposure. Recalibrating thresholds doesn't fix an underlying model that wasn't built to distinguish non-human transaction origins.

**Recommendation:** Build a separate fraud detection model trained specifically on non-human transaction patterns, running alongside the existing system. A U.K. bank case study cited: separate model reduced fraudulent applications the primary system couldn't catch.

## Gap 2 — Authentication

Existing auth requires human action at payment time (tap, scan, enter code). PSD3 (EU) addresses this by allowing authentication once at setup, not per transaction — but banks can't wait for legislative clarity while agent payments are already happening.

**Recommendation:** Move authentication upstream to agent onboarding. The trust decision is made once; per-transaction checks become redundant. This is an ownership problem before it's a technical one — one executive must be named to lead it across security, product, and legal.

## Gap 3 — API infrastructure

Banking APIs are designed for human-paced interactions. Agents execute sequences of interdependent transactions at machine velocity. **Accenture survey of 200+ CTOs and heads of payments: 85% said current systems can't handle autonomous agent-initiated transactions at scale.**

**Recommendation:** Don't replace core systems (too slow, too risky). Build a capable agent-friendly front end that handles agent requests while existing systems run normally. Goldman Sachs cited making APIs AI-agent-friendly as a key strategic focus.

---

## Key stats

- **Accenture:** 85% of 200+ CTOs say current systems can't handle autonomous agent transactions at scale
- **Deloitte:** Agentic commerce could reach **$17.5 trillion** in global commerce by 2030

## Relevance to agentic money

Banks are the infrastructure layer that agent payments must clear through. This article maps where the friction will be on the bank side — fraud detection, authentication, and API throughput. All three gaps represent either bottlenecks or opportunities for the infrastructure players ([[x402]], [[mpp]], [[ap2]]) building the agent-facing layer.

## Related pages

- [[bank-readiness-agentic-payments]]
- [[x402]]
- [[mpp]]
- [[ap2]]
- [[dimitar-dimitrov]]
