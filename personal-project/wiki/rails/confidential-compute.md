---
title: "Confidential Compute"
type: rail
topic: personal-project
tags: [confidential-compute, tee, nitro, tdx, trust, security]
sources: []
created: 2026-04-22
updated: 2026-04-22
---

# Confidential Compute

**Type:** execution infrastructure
**One-line:** Hardware-enforced isolated execution environments (TEEs) that allow computation on sensitive data without the platform operator or specialist being able to observe the raw data.

**TODO: expand**

## How it works

Trusted Execution Environments (TEEs) are hardware-enforced secure enclaves where code runs in isolation — the OS, hypervisor, and even the cloud provider cannot access the data inside. Combined with remote attestation, a client can cryptographically verify that their data was processed only by the approved code in an approved environment.

## Relevant technologies

- **AWS Nitro Enclaves** — managed TEE on AWS; easier to use, less flexible
- **Intel TDX (Trust Domain Extensions)** — hardware VM-level isolation; more control, more complexity
- **AMD SEV (Secure Encrypted Virtualization)** — alternative hardware approach

## Agent-friendliness

High for trust guarantees. Performance overhead varies (Nitro adds ~10-20ms; TDX depends on workload). For judgment-heavy tasks (research, legal analysis), this overhead is acceptable.

## Our relationship

Confidential compute is a key differentiator for financial services clients handling non-public information. It lets us claim "your data cannot leave the enclave" rather than asking clients to trust our contractual commitments.

## Open questions

- Is Nitro sufficient for our initial financial services clients, or do they require TDX?
- Does confidential compute add enough latency to impact use cases?

## Sources

*TODO: ingest Nitro/TDX technical documentation*
