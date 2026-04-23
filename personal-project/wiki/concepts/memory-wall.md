---
title: "Memory Wall"
type: concept
topic: personal-project
tags: [memory-wall, long-running-jobs, context, failure-modes]
sources: [mindstudio-memory-wall.md, lost-in-the-middle-liu-2023.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Memory Wall

**One-line:** The structural failure of AI agents on long-running jobs, caused by five compounding failure modes that larger context windows do not fix.

**TODO: expand from sources**

## Five failure modes

1. **Context overflow mid-job** — agent runs out of tokens and crashes or silently truncates
2. **Instruction dilution** — original task instructions get pushed to the "middle" of context where model attention is weakest (see: [[lost-in-the-middle-liu-2023]])
3. **Error accumulation** — partial failures cascade; downstream steps build on corrupted intermediate state
4. **State loss on interruption** — no native persistence across sessions; a restart means starting over
5. **Evaluation blindness** — agent delivers confident-sounding wrong output; nobody detects the failure

## Why bigger context windows don't fix it

Attention quality degrades across long contexts. Cost and latency scale with context length. State still doesn't persist across sessions. Error and noise accumulate faster than useful signal.

## Architectural mitigations

- Multi-agent decomposition (divide job into bounded tasks with fresh context per agent)
- External memory stores (vector DBs for retrieval instead of context accumulation)
- Checkpoint verification (verify outputs at discrete phases)
- Stateful workflow engines (treat the job as a graph with persistent state, not a single loop)

## Why this matters for the startup

The memory wall is the primary reason complex jobs need decomposition. Decomposition across agents from different organizations requires the trust, discovery, and verification layers we are building. The wall is the opening.

## Related pages

[[the-five-problems]]
[[discovery-problem]]
[[sandboxed-execution]]

## Sources

- [[mindstudio-memory-wall]] (MindStudio blog, 2026-03-21)
- [[lost-in-the-middle-liu-2023]] (Liu et al., Stanford, 2023)
