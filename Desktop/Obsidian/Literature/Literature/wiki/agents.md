# AGENTS.md — Literary Research Wiki Schema

> This file is the governing schema for the LLM-maintained literary knowledge base.
> It defines the wiki's structure, conventions, and the workflows the LLM agent must follow
> when ingesting sources, answering queries, maintaining pages, and performing health checks.
> The agent reads this file at the start of every session before touching any other file.

---

## 1. Purpose and Scope

This wiki supports research in the **history of literature** and the **critical review of books**.
It is not a neutral fact-store. It is an *interpretive* knowledge base: it accumulates not only
bibliographic and historical data, but critical arguments, competing readings, scholarly
controversies, and the human's own evolving analytical positions.

The wiki distinguishes between:

- **Information** — verifiable facts (dates, editions, biographical data, publication history)
- **Interpretation** — critical readings, thematic analyses, arguments about meaning
- **Reception** — how a work has been read, reviewed, taught, and contested over time
- **Synthesis** — the human researcher's own emerging positions, developed through inquiry

The agent handles all four, but must *never flatten* interpretive disagreement into false consensus.
Where scholars disagree, the wiki flags the disagreement and maps it — it does not resolve it.

---

## 2. Directory Structure

```
wiki/
├── AGENTS.md              ← this file (schema and instructions)
├── index.md               ← master catalog of all wiki pages
├── log.md                 ← append-only chronological record
│
├── works/                 ← one page per literary work
├── authors/               ← one page per author
├── translators/           ← one page per translator (when critically discussed)
├── publishers/            ← one page per publisher
├── genres/                ← one page per major genre family (Novel, Essay, Short Fiction, Documentary Forms)
├── periods/               ← one page per literary period or movement
├── themes/                ← one page per recurring theme or motif
├── concepts/              ← one page per critical or theoretical concept
├── critics/               ← one page per critic, scholar, or theorist
├── contexts/              ← historical, cultural, and biographical context pages
├── receptions/            ← reception history pages (one per work or author)
├── comparisons/           ← comparative analyses (cross-work, cross-author)
├── syntheses/             ← the human's own analytical positions and arguments
└── sources/               ← one summary page per ingested source document
```

Raw source documents (books, articles, reviews, notes) are stored outside the wiki in `raw/`
and are never modified by the agent. The wiki is what the agent writes and maintains.

---

## 3. Page Types and Templates

### 3.1 Work Page (`works/`)

Filename: `works/[author-surname]_[short-title].md`
Example: `works/austen_pride-and-prejudice.md`

```markdown
---
type: work
title: [Full Title in Spanish — the reviewed edition]
original_title: [Title in the original language — or "[not specified in source]"]
author: [Author Name]
first_published: [Year]
original_language: [Language]
genre: [Novel / Poetry / Drama / Essay / etc.]
period: [Literary period — links to periods/]
translator: [Translator Name(s) for the edition reviewed — or "N/A (original language)"]
publisher: [Name of the publishing house for the reviewed edition — or "" if unknown]
publisher_url: [URL to the work's page on the publishing house website — or "" if unknown]
sources_count: [number of ingested sources touching this work]
last_updated: [YYYY-MM-DD]
---

# [Full Title]

## Bibliographic Summary
[Publication history, key editions, translation history if relevant.]

## Synopsis
[Brief, neutral plot or content summary — 100–200 words maximum.]

## Critical Overview
[Synthesis of major scholarly positions. Each named position must cite its source page.]

## Interpretive Controversies
[Explicitly map competing readings. Use the format below:]

### Controversy: [Name of the dispute]
- **Position A** ([Critic/School] — see `critics/` or `sources/`): [summary]
- **Position B** ([Critic/School] — see `critics/` or `sources/`): [summary]
- **Status**: Unresolved / Dominant reading is A / Both positions active in scholarship

## Themes and Motifs
[Bulleted list linking to `themes/` pages.]

## Intertextual Connections
[Links to other works pages with a brief note on the connection.]

## Reception History
[Link to `receptions/` page if one exists, plus a brief summary.]

## The Human's Position
[The researcher's own reading or argument — clearly marked as such. Updated as the wiki evolves.]

## Sources
[Links to all `sources/` pages that inform this page.]
```

---

### 3.2 Author Page (`authors/`)

Filename: `authors/[surname]_[firstname].md`

```markdown
---
type: author
name: [Full Name]
born: [Year, Place]
died: [Year, Place — or "living"]
nationality: [Nationality]
period: [Primary literary period]
genres: [list]
last_updated: [YYYY-MM-DD]
---

# [Author Name]

## Biographical Context
[Key life events relevant to the literary work. Not a full biography — only what illuminates the writing.]

## Major Works
[Linked list to works/ pages, with one-line characterisation of each.]

## Style and Technique
[Critical overview of the author's craft: voice, structure, characteristic devices.]

## Critical Reputation
[How the author has been positioned in literary history. Include shifts over time.]

## Scholarly Controversies
[Disputed questions about authorship, biography, intention, or canonical status.]

## Sources
[Links to ingested source pages.]
```

---

### 3.3 Period Page (`periods/`)

Filename: `periods/[period-name].md`
Example: `periods/victorian.md`, `periods/magical-realism.md`

```markdown
---
type: period
name: [Period or Movement Name]
approximate_dates: [e.g. 1837–1901 / mid-20th century]
geography: [primary literary geography]
last_updated: [YYYY-MM-DD]
---

# [Period / Movement Name]

## Overview
[Historical and cultural context. What defines this period in literary terms.]

## Key Authors
[Linked list to authors/ pages.]

## Key Works
[Linked list to works/ pages.]

## Defining Characteristics
[Aesthetic, formal, thematic features. Link to themes/ and concepts/ where relevant.]

## Scholarly Debates
[How the period is contested: its boundaries, its canon, its definition.]

## Sources
```

---

### 3.4 Theme Page (`themes/`)

Filename: `themes/[theme-name].md`

```markdown
---
type: theme
name: [Theme or Motif]
last_updated: [YYYY-MM-DD]
---

# [Theme / Motif]

## Definition
[How this theme is understood in literary scholarship — not a generic definition but its critical usage.]

## Appearances
[Table or linked list: Work | Author | Notes on how theme manifests]

## Critical Treatments
[Which scholars or schools have made this theme central to their readings.]

## Cross-References
[Links to related themes/, concepts/, periods/.]

## Sources
```

---

### 3.5 Concept Page (`concepts/`)

Filename: `concepts/[concept-name].md`
Example: `concepts/free-indirect-discourse.md`, `concepts/unreliable-narrator.md`

```markdown
---
type: concept
name: [Critical or Theoretical Concept]
origin: [Who coined or developed it, and when]
field: [e.g. Narratology / New Criticism / Postcolonial Theory]
last_updated: [YYYY-MM-DD]
---

# [Concept Name]

## Definition
[Precise scholarly definition.]

## History of the Concept
[How it developed, who refined it, how its meaning has shifted.]

## Applications in This Wiki
[Links to works/ or authors/ pages where this concept is applied.]

## Critiques of the Concept
[Scholarly objections or limitations.]

## Sources
```

---

### 3.6 Critic/Scholar Page (`critics/`)

Filename: `critics/[surname]_[firstname].md`

```markdown
---
type: critic
name: [Full Name]
dates: [born–died or born–]
school_or_approach: [New Criticism / Structuralism / Feminist / etc.]
key_works: [list of their critical works]
last_updated: [YYYY-MM-DD]
---

# [Critic Name]

## Critical Position
[Their central claims and methods. What school or tradition do they represent.]

## Key Arguments
[Bullet summary of their most influential interventions.]

## Works Discussed
[Links to works/ pages where this critic's readings are cited.]

## Controversies and Responses
[Who has disputed their positions and on what grounds.]

## Sources
```

---

### 3.7 Reception Page (`receptions/`)

Filename: `receptions/[author-surname]_[short-title].md`

```markdown
---
type: reception
subject: [Work or Author]
last_updated: [YYYY-MM-DD]
---

# Reception History: [Work or Author]

## Contemporary Reception
[How the work was received upon publication — reviews, controversies, initial reputation.]

## 20th-Century Critical Shifts
[Major reappraisals, academic canonisation or marginalisation.]

## Current Scholarly Status
[Where the work stands today: canonical / contested / neglected / recovered.]

## Notable Rereadings
[Specific critical works that substantially shifted the reception. Link to sources/.]

## Sources
```

---

### 3.8 Source Summary Page (`sources/`)

Filename: `sources/[YYYY-MM-DD]_[short-title].md`

```markdown
---
type: source
title: [Full title of the source]
author: [Author(s)]
date_ingested: [YYYY-MM-DD]
source_type: [Monograph / Article / Review / Book chapter / Primary text / Other]
wiki_pages_affected: [list of pages updated on ingest]
---

# Source: [Short Title]

## Bibliographic Details
[Full citation in a consistent format.]

## Summary
[200–400 words. The LLM's synthesis of the source's argument or content — not quotation.]

## Key Claims
[Bulleted list of the most important assertions, findings, or arguments.]

## Relation to Existing Wiki
[What this source adds, challenges, or refines. Where it contradicts existing pages, flag it explicitly.]

## Quotations of Significance
[Verbatim passages worth preserving — scholarly judgment required. Keep to minimum.]

## Limitations or Biases
[Any methodological limits, dated assumptions, or known scholarly critiques of this source.]
```

---

### 3.9 Synthesis Page (`syntheses/`)

Filename: `syntheses/[YYYY-MM-DD]_[descriptive-title].md`

These pages record the **human researcher's own positions**. The agent may help draft them
based on conversation, but must mark them clearly and never confuse them with sourced claims.

```markdown
---
type: synthesis
title: [Descriptive title of the argument or position]
date: [YYYY-MM-DD]
related_works: [links]
related_sources: [links]
status: [Draft / Developing / Stable]
---

# [Title]

## Argument
[The human's interpretive position, in their own words or developed collaboratively.]

## Supporting Evidence
[Links to sources/ and wiki pages that support this position.]

## Outstanding Questions
[What remains unresolved or requires further reading.]

## Revision History
[Brief log of how this position has changed as more sources were ingested.]
```

---

### 3.10 Translator Page (`translators/`)

Filename: `translators/[surname]_[firstname].md`
Example: `translators/saenz_miguel.md`

**When to create**: Only when a critic or source explicitly evaluates or discusses the quality, style,
or significance of the translator's work — not merely when a translator is listed as book metadata.
Translator metadata (name, publisher, edition) is recorded in the relevant `works/` and `sources/`
pages regardless of whether a translator page exists.

```markdown
---
type: translator
name: [Full Name]
born: [Year, Place — or "unknown"]
died: [Year, Place — or "living"]
nationality: [Nationality]
languages: [Source language(s) → target language(s)]
last_updated: [YYYY-MM-DD]
---

# [Translator Name]

## Profile
[Brief note on the translator's background and significance within their language pair(s).
Focus on what is relevant to the literary tradition tracked in this wiki.]

## Critical Attention
[Any evaluative commentary on the quality or character of their translations, as recorded
in wiki sources. Distinguish between praise, criticism, and comparative assessments.
Always cite the source page.]

## Works Translated in This Wiki
[Linked list to works/ pages, with source language, target language, and publisher for each.]

## Sources
[Links to source pages where this translator is explicitly discussed.]
```

---

### 3.11 Publisher Page (`publishers/`)

Filename: `publishers/[publisher-slug].md`
Example: `publishers/anagrama.md`, `publishers/libros-del-asteroide.md`

**When to create**: For every publisher that appears in a `works/` page frontmatter field.

```markdown
---
type: publisher
name: [Full Publisher Name]
city: [City — or "unknown"]
country: [Country — or "unknown"]
founded: [Year — or "unknown"]
last_updated: [YYYY-MM-DD]
---

# [Publisher Name]

## Editorial Profile
[What kind of books they publish — observed from the wiki catalog and general knowledge.
Mark general knowledge claims as [unsourced — verify].]

## Works in This Wiki

| Title | Author | Language | First Published | Genre |
|-------|--------|----------|-----------------|-------|

## Thematic Trends
[Aggregate the recurring themes across their catalog in this wiki. Note patterns:
languages they translate from, genres they favour, periods they return to.]

## Sources
[Links to all works/ pages for this publisher.]
```

---

## 4. Workflows

### 4.1 Ingest a New Source

When the human adds a source to `raw/` and asks the agent to process it:

1. Read the source fully.
2. Discuss key takeaways with the human before writing anything.
3. Create a `sources/` page with full summary and key claims.
4. Identify every wiki page this source is relevant to.
5. Update each affected page: add to the Sources section, update relevant sections, flag any contradictions with existing content using `[!contradiction]` callouts.
6. If the source is a review of a translated work, record the translator name(s) in the `sources/` page and in the `translator:` frontmatter field of the `works/` page. If the source explicitly evaluates the translator's work (not just names them), create or update a `translators/` page.
7. Update `index.md`: add the new source page and any new pages created.
8. Append an entry to `log.md`.
9. Report to the human: list all pages touched and any contradictions flagged.

A single source may touch 5–20 wiki pages. This is expected and desirable.

**Critical discipline**: when updating a `works/` page with a new critical reading, do not overwrite
existing readings — add the new position and explicitly mark where it agrees with, extends, or
disputes positions already recorded.

### 4.2 Answer a Query

When the human asks a question:

1. Read `index.md` to identify relevant pages.
2. Read the relevant pages in full.
3. Synthesise an answer with explicit page citations.
4. If the answer involves an interpretive question, map the positions — do not pick a winner unless the human asks for the agent's assessment.
5. Ask the human: "Should I file this answer as a synthesis page?" If yes, create it in `syntheses/`.

### 4.3 Lint the Wiki

When asked to health-check the wiki:

- Find pages with no inbound links (orphans).
- Find works, authors, or critics mentioned in page text but lacking their own page.
- Find contradictions that have been flagged but not yet reviewed by the human.
- Find source pages that have not propagated their key claims to relevant entity pages.
- Find synthesis pages marked "Draft" that have not been updated in more than 30 days.
- Find work pages where `translator` contains "not specified" or is empty for a translated work (i.e., `original_language` ≠ Spanish).
- Find work pages where `publisher_url` is empty (`""`).
- Suggest new questions the human might investigate, and new sources to seek out.

Report findings as a structured list. Do not auto-fix — present to the human for decisions.

---

## 5. Critical Discipline Rules

These rules govern the agent's interpretive behaviour and are non-negotiable.

**Rule 1 — No false synthesis.**
When two critics or schools disagree, map the disagreement. Do not produce a
"balanced view" that papers over the conflict. The conflict is the content.

**Rule 2 — Source every claim.**
Every critical assertion on a wiki page must link to a `sources/` page. Unsourced
claims must be marked `[unsourced — verify]`.

**Rule 3 — Distinguish information from interpretation.**
Bibliographic facts (first publication date, author's name) are information.
Readings, arguments, and valuations are interpretation. They must be presented differently.

**Rule 4 — Preserve the human's voice in syntheses.**
Synthesis pages belong to the researcher. The agent may draft, but must not impose
interpretive positions. When in doubt, ask.

**Rule 5 — Flag theoretical framework.**
When recording a critical reading, always note what theoretical framework it uses
(e.g., Marxist, feminist, narratological, historicist). Readings from different frameworks
are not simply contradictions — they are often answers to different questions.

**Rule 6 — Treat reception history as evidence.**
How a work has been read is itself a historical fact, as significant as any formal analysis.
Reception pages are not secondary — they are primary data about literary history.

**Rule 7 — Never summarise a primary text as if summary were analysis.**
A plot summary is not a reading. When ingesting a primary literary text, the agent produces
a synopsis, but must not present it as critical interpretation. Interpretation requires argument.

---

## 6. Conventions

- **Dates**: ISO format (YYYY-MM-DD) in frontmatter; prose dates written out (e.g., "April 1847").
- **Citations**: Use inline links to `sources/` pages. Format: `[Author, Short Title](../sources/page.md)`.
- **Contradiction callouts**: `> [!contradiction] [source A] contradicts [source B] on [specific claim]. Unresolved.`
- **Uncertainty markers**: `[unsourced — verify]`, `[date uncertain]`, `[attribution disputed]`
- **The human's voice**: Any passage written by the human or representing their position is marked `> [Human's note: ...]`
- **Linking**: All proper nouns with their own wiki pages must be linked on first mention in each page.
- **Page length**: Source summaries: 300–600 words. Entity pages: as long as the material warrants. No padding.
- **Translators**: Record translator name(s) in the `translator:` frontmatter field of every `works/` page for a translated text. In prose, cite as "Trans. [Name]" on first mention. Create a `translators/` page only when a source provides critical commentary on the translation — not for metadata-only mentions. If multiple translators worked on a single text (e.g., Spanish and Catalan editions), list all with their respective editions.

---

## 7. What the Agent Must Not Do

- Do not delete or overwrite existing interpretive content — only add, update, or flag.
- Do not resolve scholarly controversies by choosing a side without the human's instruction.
- Do not invent citations or attribute claims to sources not in the `raw/` collection.
- Do not produce a synthesis page without the human's involvement.
- Do not treat any single critical school as the default or neutral position.
- Do not summarise primary literary texts as if that were literary analysis.
