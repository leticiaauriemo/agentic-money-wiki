# Activity Log — Personal Project

Append-only activity record. Format: `## [YYYY-MM-DD] type | description`
Types: `ingest` | `query` | `lint` | `init` | `update`

Parse recent entries: `grep "^## \[" _log.md | tail -10`

---

## [2026-04-23] update | Expanded three remaining concept stubs

- sandboxed-execution.md: full expansion — Tomašev delegation axes (verifiability/reversibility) for isolation calibration; technical layers (compute isolation, data scoping, egress controls, TEEs, output verification); specialist incentive mitigations; what sandboxing enables that contracts cannot
- client-context-moat.md: full expansion — Guo memory-enhanced discovery as academic basis; what accumulates over time (routing priors, constraints, format calibration, specialist-client fit, exception patterns); Rothschild preference economy framing; diversity requirement from El et al.; risks and mitigations
- continuous-evaluation.md: full expansion — evaluation infrastructure gap (Kapoor HAL: scaffolds matter, log analysis, reasoning effort paradox); first-proposal bias 10-30x (Bansal); four evaluation layers (synthetic benchmarks, anonymized real jobs, outcome tracking, staked reputation); quality flywheel across four timescales; Deng lifecycle trustworthiness commitment; El et al. diversity finding applied to reputation
- _index.md: updated concept table summaries to reflect expanded content

---

## [2026-04-23] ingest | Full batch ingest — all 18 remaining sources

All sources from raw/ ingested. Summary pages created for:
- ioa-agent-discovery-guo-2025 (two-stage capability discovery; verification as the hard layer)
- lost-in-the-middle-liu-2023 (U-shaped attention curve; empirical basis for instruction dilution)
- mindstudio-memory-wall (practitioner framing; tasks vs. jobs vocabulary)
- mindstudio-discovery-problem (three-layer discovery; MCP as power outlet)
- ai-agent-market-liu-2026 (40.3x cost advantage; 7-layer market design; Agents of Chaos governance)
- magentic-marketplace-bansal-2025 (first-proposal bias 10-30x; scale degrades performance)
- holistic-agent-leaderboard-kapoor-2025 (scaffolds matter; evaluation infrastructure gap; shortcuts)
- intelligent-ai-delegation-tomasev-2026 (verifiability/reversibility axes; certifiable agentic capabilities)
- internet-of-agents-chen-2024 (dynamic team formation; third-party agent integration)
- prime-planning-zou-stanford-2025 (MCTS orchestration; decomposition as option discovery)
- meta-agent-inefficiencies-el-stanford-2025 (meta-agents don't improve from all history; low diversity)
- modular-decomposition-multiagent-pan-2025 (attention-weighted decomposition; global consistency)
- agent-subagent-skill-tool-piskala-2026 (control-axis taxonomy; autonomy earned through necessity)
- agentic-services-computing-deng-2025 (ASC paradigm; lifecycle; behavioral trustworthiness)
- gdpval-openai-2025 (frontier models approaching expert quality on professional tasks)
- metr-long-task-completion-2025 (110-min time horizon; doubling every 7 months)
- darwin-godel-machine-zhang-2025 (self-improving agents; open-ended evolution; SWE-bench 20%→50%)
- personal-notes-ideas (user fragments; market framing quote on property rights)

Key new strategic insights from batch:
- 40.3x cost advantage of specialists (Liu) — most quotable data point
- First-proposal bias 10-30x in agentic markets (Bansal) — confirms need for quality-ranked routing
- Scaffolds matter as much as models (Kapoor) — platform design is the value, not raw model choice
- Time horizon doubling every 7 months, may be accelerating (METR) — window for this business is limited
- Meta-agents produce low-diversity agents (El et al.) — curated specialist diversity remains valuable

---

## [2026-04-22] ingest | Ingested agentic-economy-rothschild-2025.pdf

- Created summary-agentic-economy-rothschild-2025.md in analysis/
- Key insight: paper names exactly the startup's gap — web of agents requires "discovery, trust, security" mechanisms that don't yet exist
- "Preference economy" framing (quality feedback as scarce resource) maps to continuous-evaluation flywheel
- Walled garden vs. open web framing reinforces the neutral enterprise trust layer positioning
- Updated overview.md: wedge corrected to management consulting + policy research (was "financial services research")
- Updated _index.md: added summary to ingested sources table

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
