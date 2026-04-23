---
title: "Sandboxed Execution"
type: concept
topic: personal-project
tags: [trust, security, sandbox, isolation, confidential-compute]
sources: []
created: 2026-04-22
updated: 2026-04-22
---

# Sandboxed Execution

**One-line:** The technical enforcement of isolation between a client's data and a specialist agent — making cross-org trust a system property, not a contract.

**TODO: expand from sources**

## What it means in this context

When a client's agent sends a subtask to a specialist, the specialist:
- Sees only the data scoped to that subtask (data isolation)
- Cannot contact the client or any external system outside the platform (in-platform communication enforcement)
- Cannot exfiltrate data through side channels
- Operates in a reproducible, auditable environment
- Produces outputs that can be verified before delivery

## Technical approaches

- **Docker / Firecracker** — lightweight VM isolation for fast spin-up
- **AWS Nitro Enclaves** — managed confidential compute with attestation
- **Intel TDX / AMD SEV** — hardware-level trusted execution environments
- **In-platform communication** — all specialist outputs go through platform verification before reaching client

## Why this is hard

Specialists have incentive to over-claim capability and to collect data for training or competitive intelligence. Sandboxing must prevent both without adding so much friction that specialists won't participate.

## Open questions

- What's the minimum sandboxing that a financial services client would accept?
- Does confidential compute add enough latency to matter for our use cases?
- How do we prevent specialists from encoding data in natural language outputs?

## Related pages

[[the-five-problems]]
[[confidential-compute]]
[[client-context-moat]]
