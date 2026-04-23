# Wiki — Root Schema

This is a multi-topic personal knowledge base maintained by Claude Code.
The human curates sources and asks questions. Claude does all writing, cross-referencing, and maintenance.

## Repository layout

```
wiki/                        ← Obsidian vault root (open this folder)
  CLAUDE.md                  ← this file: root-level conventions
  agentic-money/             ← topic folder
    CLAUDE.md                ← topic-specific schema (read this when working in that topic)
    raw/                     ← immutable source documents (never edit)
      assets/                ← images downloaded from articles
    wiki/                    ← LLM-maintained markdown pages
      _index.md              ← master page catalog (update on every ingest)
      _log.md                ← append-only activity log
      overview.md            ← synthesis overview of the topic
      companies/             ← one page per company/org
      concepts/              ← one page per concept or technology
      rails/                 ← payment rails, protocols, infrastructure
      use-cases/             ← specific use case breakdowns
      players/               ← individuals, regulators, coalitions
      analysis/              ← saved query answers, comparisons, synthesis
```

To add a new topic: create a new folder at this level, copy the structure above, and write a CLAUDE.md for it. Document the entity types relevant to that domain.

## General conventions (apply to all topics)

### File naming
- Lowercase, hyphenated: `stripe-stablecoin-strategy.md`
- No spaces, no special characters
- Page titles go in the frontmatter `title:` field and as the H1 heading

### Frontmatter (every wiki page)
```yaml
---
title: "Page Title"
type: company | concept | rail | use-case | player | summary | analysis | overview
topic: agentic-money          # the parent topic folder name
tags: []
sources: []                   # list of raw/ filenames that informed this page
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

### Frontmatter (summary pages only — add `source_type`)
```yaml
---
title: "Page Title"
type: summary
topic: agentic-money
source_type: news | company-blog | report | academic | analysis | social | transcript
tags: []
sources: []
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

`source_type` values:
- `news` — journalism, press coverage
- `company-blog` — official announcements, product launches
- `report` — research reports, whitepapers, industry studies
- `academic` — papers, peer-reviewed studies
- `analysis` — newsletters, opinion pieces (e.g. Fintech Brainfood)
- `social` — X threads, LinkedIn posts (paste into `.txt` manually — Web Clipper unreliable on X)
- `transcript` — podcast or video transcripts

### Wikilinks
Always use Obsidian wikilinks for internal references: `[[filename]]` or `[[filename|display text]]`.
Do not use relative markdown paths. The graph view depends on wikilinks.

### Cross-referencing discipline
When you create or update a page, ask: what other pages mention this entity?
Go update those pages to link back. Cross-references should be bidirectional.

### Contradictions
When new source material contradicts an existing wiki claim, do not silently overwrite.
Add a `> **Note (YYYY-MM-DD):** [new source] contradicts the above — [brief explanation].` blockquote inline.

### Source immutability
Never edit files in `raw/`. Read from them; write only to `wiki/`.

## Working with multiple topics
When the user specifies a topic (or it's clear from context), read that topic's `CLAUDE.md` before starting work.
If a concept spans multiple topics, create the page in the most relevant topic and wikilink to it from the other.

## Session startup
At the start of each session:
1. Read this file
2. Read the relevant topic's `CLAUDE.md`
3. Read `<topic>/wiki/_log.md` (last 10 entries) to understand recent activity
4. Read `<topic>/wiki/_index.md` to understand what pages exist

Then ask the user what they want to do, or proceed if the instruction is clear.

## Tools & setup

**Obsidian Web Clipper** — browser extension that converts web articles to clean markdown. Use it to get sources into `raw/` quickly. After clipping, rename the file to match the lowercase-hyphenated convention before ingesting.

**Images** — in Obsidian Settings → Files and links, set "Attachment folder path" to `raw/assets/`. Use the "Download attachments for current file" hotkey after clipping to pull images local. The LLM handles images per the ingest workflow below.

**Git** — the wiki is a plain git repo. Run `git init` from the Research folder if not already done. Commit after major ingests to get version history and the ability to roll back a bad ingest.

**Dataview** — Obsidian plugin that runs queries over page frontmatter. Useful once the wiki has dozens of pages; lets you build dynamic tables by tag, date, or type.
