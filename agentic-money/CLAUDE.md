# Agentic Money Movement — Topic Schema

**Topic:** How AI agents are moving, optimizing, and transacting money autonomously.
Covers: stablecoins, card rails, bank APIs, yield optimization, commerce, financial services, payments infrastructure, and the companies/protocols building this.

Read this file when working in the `agentic-money/` topic.
Also read the root `../CLAUDE.md` for general conventions.

---

## Research questions this wiki is trying to answer

- Where is agentic money movement happening *right now* — in production, not just announced?
- What are the underlying rails? (stablecoins, card networks, ACH, bank APIs, crypto L1/L2)
- Who are the key players — companies, protocols, regulators, investors?
- Is bank yield optimization already happening with agents? Who is doing it and how?
- How is agentic commerce being enabled — shopping, subscriptions, micro-payments?
- Where is this going in 2–3 years? What are the bottlenecks (regulatory, technical, trust)?
- How do identity, KYC, and compliance work in an agent-initiated transaction?

---

## Entity types and page structure

### `companies/` — companies and organizations
One page per company building in this space.

```markdown
---
title: "Company Name"
type: company
topic: agentic-money
tags: [stablecoin, payments, infrastructure, ...]   # pick relevant tags
founded: YYYY
stage: public | private | acquired | defunct
hq: City, Country
sources: []
created: YYYY-MM-DD
updated: YYYY-MM-DD
---

# Company Name

**One-line:** What they do in one sentence.

## What they're building
[2–4 sentences on their product/approach]

## Relevance to agentic money
[Why this company matters to this research area]

## Funding & traction
[Key funding rounds, notable metrics if public]

## Key people
- [[person-name]] — role

## Products / offerings
- Product name: brief description

## Partnerships & integrations
- [[other-company]] — nature of relationship

## Open questions
- [Things we don't know yet about this company]

## Sources
- [[source-filename]]
```

### `concepts/` — technologies, mechanisms, ideas
One page per distinct concept.

```markdown
---
title: "Concept Name"
type: concept
topic: agentic-money
tags: []
sources: []
created: YYYY-MM-DD
updated: YYYY-MM-DD
---

# Concept Name

**One-line:** [Plain English definition]

## How it works
[Technical or operational explanation, 3–6 sentences]

## Why it matters for agentic money
[Connection to the research area]

## Current state
[What exists today vs. what's theoretical]

## Key players using / building this
- [[company-name]]

## Related concepts
- [[related-concept]]

## Sources
- [[source-filename]]
```

### `rails/` — payment infrastructure and protocols
One page per rail, network, or protocol.

```markdown
---
title: "Rail / Protocol Name"
type: rail
topic: agentic-money
tags: []
sources: []
created: YYYY-MM-DD
updated: YYYY-MM-DD
---

# Rail Name

**Type:** blockchain / card network / bank API / messaging protocol / ...
**One-line:** [What it is]

## How it works
## Settlement speed & cost
## Who controls it
## Agent-friendliness
[Is this rail usable by software agents? What are the friction points?]
## Who is building on it
## Regulatory status
## Sources
```

### `use-cases/` — specific real-world applications
One page per distinct use case.

```markdown
---
title: "Use Case Name"
type: use-case
topic: agentic-money
tags: []
sources: []
created: YYYY-MM-DD
updated: YYYY-MM-DD
---

# Use Case Name

**One-line:** [What the agent is doing with money]

## How it works today
## Who is doing this (in production)
- [[company-name]] — how they implement it
## Technical requirements
## Regulatory considerations
## Status: live | pilot | announced | theoretical
## Sources
```

### `analysis/` — saved query answers and synthesis
One page per saved query answer, comparison, or analytical synthesis.
Default filename: `analysis/question-slug.md` (type: analysis).
Always ask the user whether to file a query answer before discarding it.

### `players/` — individuals, regulators, coalitions
One page per notable person, regulator, or industry group.

```markdown
---
title: "Name"
type: player
topic: agentic-money
tags: [regulator | founder | investor | researcher]
sources: []
created: YYYY-MM-DD
updated: YYYY-MM-DD
---

# Name

**Role:** [Current role / organization]
**Relevance:** [Why they matter to this space]

## Views / positions
## Actions taken
## Sources
```

---

## Ingest workflow

When the user drops a new source into `raw/` and says "ingest":

1. **Read the source** fully before doing anything. If the source references images in `raw/assets/`, read the text first, then view the relevant images separately to capture any additional context (charts, diagrams, screenshots).
2. **Discuss key takeaways** with the user — what's interesting, what's surprising, what needs emphasis. Wait for their input before writing if they want to be involved.
3. **Write a summary page** in `wiki/` (type: summary) with filename matching the source file, e.g. `raw/stripe-stablecoin-report.pdf` → `wiki/stripe-stablecoin-report.md`. Set `source_type` in the frontmatter: `news | company-blog | report | academic | analysis | social | transcript`.
4. **Update or create entity pages**: for every company, concept, rail, use case, or player mentioned significantly in the source, update the relevant page or create it if it doesn't exist.
5. **Update `_index.md`**: add the new summary page and any new entity pages.
6. **Update `overview.md`**: revise the synthesis if the source changes or strengthens the picture.
7. **Append to `_log.md`**: one entry with format `## [YYYY-MM-DD] ingest | Source Title`.

A single source will typically touch 5–15 wiki pages. This is expected and correct.

---

## Query workflow

When the user asks a question:

1. Read `_index.md` to identify relevant pages.
2. Read those pages.
3. Synthesize an answer with wikilink citations.
4. **Ask the user if they want the answer filed as a wiki page.** Good analyses, comparisons, and synthesis answers should be saved — they compound the wiki just like sources do. Default filename: `wiki/analysis/question-slug.md` (type: analysis).

---

## Lint workflow

When the user asks to "lint the wiki":

1. Check for orphan pages (no inbound wikilinks) — report them.
2. Check for pages mentioned in other pages but not yet created — create stubs or flag them.
3. Check for claims marked with contradiction notes — are they resolved?
4. Check `overview.md` — is it still current given everything ingested?
5. Suggest 3–5 follow-up sources or questions that would fill notable gaps.
6. Append a lint entry to `_log.md`.

---

## Key tags for this topic

Use these consistently in frontmatter:

`stablecoin` `card-rails` `bank-api` `yield-optimization` `agentic-commerce` `identity-kyc` `compliance` `crypto-l1` `crypto-l2` `infrastructure` `wallet` `payment-processor` `neobank` `regulator` `shopping` `subscriptions` `b2b-payments` `cross-border` `open-banking`

---

## Seeded open questions (as of wiki creation)

These are the initial gaps to fill through research:

- Which companies have *shipped* agent-initiated payments (not just announced)?
- Is any bank or fintech running yield optimization bots on customer accounts today?
- What is the compliance/KYC story when an agent initiates a transaction — who is liable?
- How do Visa/Mastercard rails handle agent-initiated card transactions? Any special programs?
- What stablecoins are actually being used for commerce vs. just trading?
- Who are the infrastructure picks-and-shovels players (not the consumer-facing ones)?
