# Activity Log — Personal Project

Append-only activity record. Format: `## [YYYY-MM-DD] type | description`
Types: `ingest` | `query` | `lint` | `init` | `update`

Parse recent entries: `grep "^## \[" _log.md | tail -10`

---

## [2026-04-22] update | Expanded three core concept pages

- memory-wall.md: full expansion from stub — five failure modes, tasks vs. jobs distinction, why bigger context doesn't fix it, architectural responses, PRIME (Stanford MCTS), connection to startup thesis
- discovery-problem.md: full expansion — three layers, IoA framework (Guo et al.), why trust is the hardest layer, what a full solution requires
- subagents-and-orchestration.md: new page — tool/skill/subagent/agent taxonomy (Piskala), clean room data flow model, PRIME orchestration, modular decomposition (Pan et al.), specialist vs. generalist routing question
- econ136-proposal.md: revised proposal — dropped auction framing, centered on market formation failure and substitutes for missing social infrastructure
- _index.md: updated to reflect new and revised pages

---

## [2026-04-22] init | Wiki initialized

- Created folder structure following root CLAUDE.md conventions
- Wrote topic-level CLAUDE.md with thesis, entity types, priority ingest order
- Moved and renamed 19 source files from Notes/ to raw/:
  - Identified all PDFs from arxiv IDs; deleted 1 duplicate (2510.11977v1 (1).pdf)
  - Key sources confirmed: agentic-economy-rothschild-2025.pdf, ioa-agent-discovery-guo-2025.pdf, lost-in-the-middle-liu-2023.pdf, both MindStudio articles
  - Notable additions: prime-planning-zou-stanford-2025.pdf (Stanford MCTS paper), meta-agent-inefficiencies-el-stanford-2025.pdf (Stanford critique), intelligent-ai-delegation-tomasev-2026.pdf (DeepMind)
- Seeded wiki with 4 core pages: overview, the-five-problems, competitive-landscape, open-questions
- Created 6 company stubs: mindstudio, aws-agentcore, mem0, letta, coinbase-agentic-market, stripe-mpp
- Created 5 concept stubs: memory-wall, discovery-problem, sandboxed-execution, client-context-moat, continuous-evaluation
- Created 5 rails stubs: mcp, a2a, x402, mpp, confidential-compute
- Initialized _index.md and _log.md
- Sources still needed: a16z missing infrastructure article, Coinbase Agentic.market launch coverage
- Next: ingest priority sources starting with agentic-economy-rothschild-2025.pdf
