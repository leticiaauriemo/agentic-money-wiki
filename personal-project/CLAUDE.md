# Personal Project — Startup Research Wiki

Research and development workspace for a startup idea:
**a managed service for enterprise AI agent subcontracting.**

The core thesis:
Enterprise AI agents hit two walls — the memory wall (long jobs break)
and the discovery problem (no trusted way to find specialists across
organizational boundaries). This wiki develops the product, market,
competitive landscape, and technical architecture for a service that
solves both.

Read the root `../CLAUDE.md` for general file, frontmatter, and wikilink conventions.
Read this file when working in the `personal-project/` topic.

---

## The problem cluster

Five interlocking problems this startup addresses:

1. **Memory wall** — agents fail at long jobs (context overflow,
   instruction dilution, error cascades, state loss, evaluation blindness)
2. **Discovery** — no trusted registry of specialist agents with measured
   quality across organizational boundaries
3. **Trust and safety** — cross-org subcontracting requires sandboxed
   execution, data isolation, verification, and accountability
4. **Per-client context** — the platform accumulates per-client preferences,
   constraints, past outcomes, and specialist fit over time; this is the moat
5. **Continuous evaluation** — specialists compete on synthetic benchmarks
   and anonymized jobs; performance data feeds routing; staked reputation
   creates a quality flywheel

---

## The product

A managed service (not software) where enterprise-client agents send
complex jobs to be decomposed, routed to vetted specialists running in
a sandboxed environment, verified before delivery, with accumulated
per-client context making every subsequent job better.

Positioned as the **enterprise trust layer** on top of emerging
infrastructure (MCP, A2A, x402, confidential compute).

---

## Entity types in this topic

Use these `type:` values in frontmatter:

- `company` — MindStudio, Mem0, AgentCore, Coinbase, Stripe, etc.
- `concept` — memory wall, discovery, client context, verifier, sandbox
- `rail` — payment protocols and infrastructure (MCP, A2A, x402, MPP, TEEs)
- `use-case` — financial research, legal research, compliance monitoring
- `player` — Stanford professors, advisors, VCs, researchers
- `summary` — raw source summaries (papers, articles, blog posts)
- `analysis` — pitch drafts, competitive maps, open questions, strategic decisions
- `overview` — top-level synthesis

---

## Key questions this wiki is helping answer

- Who is my first customer?
- What vertical do I start with? (Current lean: financial services research)
- How do I keep specialists honest when they have incentive to overclaim?
- Where does AWS AgentCore stop and my service begin?
- Will foundation models make this obsolete, or make it more valuable?
- What's the minimum viable v0 I could run for one real client?
- Which Stanford professors should I talk to and in what order?

Every new source should either help answer one of these or surface a
new question worth tracking.

---

## Working conventions

Follow root `../CLAUDE.md` for file naming, frontmatter, wikilinks,
and cross-referencing.

Additional conventions for this topic:

- When summarizing a paper or article, always create the summary in
  `wiki/analysis/` or `wiki/concepts/`, link back to the raw file in
  `sources:`, and extract 1–3 key quotes with page numbers.
- When a source mentions a company, person, or concept that doesn't
  have a page yet, create a stub page with at least a one-line
  description and a `TODO: expand` note.
- When processing multiple sources in a batch, update `overview.md` at
  the end to reflect any new strategic shifts.
- Keep `analysis/open-questions.md` as a living list. Every session
  should either answer one or add one.
- Don't invent pages not justified by sources. Stubs are fine.

---

## Ingest workflow

Same as root CLAUDE.md, plus:
- Extract 1–3 key quotes with page numbers in every summary.
- Note whether the source helps answer a key question (above), and which one.
- If the source changes the competitive picture, flag it for overview.md.

---

## Priority ingests (in order)

Process these first if starting fresh:

1. `agentic-economy-rothschild-2025.pdf` — foundational framing for the whole thesis
2. `ioa-agent-discovery-guo-2025.pdf` — technical framework for the discovery problem
3. `lost-in-the-middle-liu-2023.pdf` — academic basis for memory wall / instruction dilution
4. `mindstudio-memory-wall.md` — competitor framing of problem 1 (memory wall)
5. `mindstudio-discovery-problem.md` — competitor framing of problem 2 (discovery)
6. `ai-agent-market-liu-2026.md` — market design framework, governance layer argument
7. `magentic-marketplace-bansal-2025.pdf` — Microsoft's open-source agentic market simulation
8. `holistic-agent-leaderboard-kapoor-2025.pdf` — evaluation infrastructure thesis
9. `intelligent-ai-delegation-tomasev-2026.pdf` — governance and delegation framing (DeepMind)
10. `internet-of-agents-chen-2024.pdf` — multi-agent coordination architecture
11. `prime-planning-zou-stanford-2025.pdf` — Stanford MCTS-based multi-agent planning
12. `meta-agent-inefficiencies-el-stanford-2025.pdf` — Stanford critique of meta-agent design
13. `modular-decomposition-multiagent-pan-2025.pdf` — modular task decomposition (CMU/USC)
14. Remaining papers: `agentic-services-computing`, `gdpval`, `metr-long-task-completion`, `darwin-godel-machine`

**Sources still needed (not yet in raw/):**
- a16z "missing infrastructure for AI agents" piece
- Coinbase Agentic.market launch coverage

---

## Session startup

1. Read root `../CLAUDE.md`
2. Read this file
3. Read `wiki/_log.md` (last 10 entries)
4. Read `wiki/_index.md`
5. Ask the user what they want to do, or proceed if the instruction is clear.
