---
status: Active
owner: Lino (CPO)
created: 2026-02-27
last_updated: 2026-03-09
---

# Docs Project

## Project goal

Build a customer-facing product documentation site (`docs/`) that:

1. Documents all VoiceLine features in clear, customer-oriented language
2. Presents product bundles with feature-level cross-references
3. Supports the feature hierarchy provided by the CPO — organized by product area, not use case
4. Is hostable on the VoiceLine domain and works in plain markdown
5. Includes a source map per feature (internal navigation aid for future development work)

**Success metric**: Any customer or prospect can self-navigate VoiceLine's full feature set, understand which bundle unlocks what, and find relevant documentation without help from the team.

**Style reference**: [Linear docs](https://linear.app/docs) — tone, information architecture, and page format.

---

## What this is NOT

- The internal KB (`product_documentation/`, `gtm_communications/`) is **not changing** — docs is a new layer on top
- Value calculation files (`variables.yaml`, `calculate.py`) stay in `product_documentation/` — not moving
- No ROI numbers, CPO interview notes, or internal framing in customer docs

---

## Artifacts being built

| # | Artifact | Location | Status |
|---|----------|----------|--------|
| 1 | Customer docs root | `docs/` | Phase 1 — scaffold |
| 2 | Feature map (internal) | `docs/_internal/feature_map.md` | Phase 1 |
| 3 | Cross-ref queue (internal) | `docs/_internal/cross_ref_queue.md` | Phase 1 |
| 4 | Blank spots log (internal) | `docs/_internal/blank_spots.md` | Phase 1 |
| 5 | Sources scanned index (internal) | `docs/_internal/sources_scanned.md` | Phase 1 |
| 5 | Getting started section | `docs/getting-started/` | Phase 4 |
| 6 | Feature pages (~65 pages) | `docs/[product-area]/[feature].md` | Phase 2 (batches) |
| 7 | Bundle pages (10) | `docs/bundles/` | Phase 3 |
| 8 | Area overview pages | `docs/[product-area]/index.md` | Phase 3 |
| 9 | Source maps | `product_documentation/01_features/[feature]/sources.yaml` | Phase 2 (per batch) |
| 10 | Maintenance guide | `docs/README.md` | Phase 5 |

---

## Progress tracker

### Phase 0: Feature hierarchy ✅ COMPLETE

- [x] CPO provides full feature hierarchy → `docs/hierarchy_draft.md`
- [x] Hierarchy assessed: KB coverage gaps flagged, naming decisions made
- [x] `docs/` folder structure defined from product areas
- [x] Page templates finalized (Linear-style, with Overview + Where to find it + Bundle callout)

### Phase 1: Scaffold ✅ COMPLETE

- [x] Create `docs/` folder structure (all folders + empty stub `.md` files)
- [x] Create `docs/_internal/` with seeded `feature_map.md`, empty `cross_ref_queue.md`, empty `blank_spots.md`, empty `sources_scanned.md`
- [x] Write `docs/README.md` maintenance guide stub

### Phase 2: Feature documentation (per batch) ✅ COMPLETE

- [x] Batch 1 — Workflows (13 pages) + blank spots surfaced
- [x] Batch 2 — Coaching: Playbooks + Visit Analytics
- [x] Batch 3 — Coaching: Team Activity
- [x] Batch 4 — Analytics
- [x] Batch 5 — Productivity: Visit Briefing + CRM Data Quality
- [x] Batch 6 — Productivity: Assistant
- [x] Batch 7 — Platform: Integrations (CRM pages)
- [x] Batch 8 — Platform: Data Objects
- [x] Batch 9 — Platform: remaining (admin, language, security, search, workflow customisation)
- [ ] All blank spots resolved or accepted

### Phase 3: Navigation and bundles ✅ COMPLETE

- [x] Area `index.md` for each product area (5 pages)
- [x] Commercial pages: `docs/commercial/field-sales-fundamentals.md`, `modules.md`, `platform.md`
- [x] Commercial index: `docs/commercial/index.md`

### Phase 4: Getting started ✅ COMPLETE

- [x] `docs/getting-started/index.md` — L1 landing
- [x] `docs/getting-started/platform-overview.md` — What is VoiceLine?
- [x] `docs/getting-started/quick-start.md` — First steps

### Phase 5: Finishing touches ✅ COMPLETE

- [x] Add `bundles:` field to all feature frontmatter + fix incorrect module references (38 files)
- [x] Write `docs/README.md` — maintenance guide
- [x] Verify: all links resolved (4 broken fixed), no internal content leaked (1 instance cleaned), all features mapped

---

## Folder structure

Sidebar shows **L1 + L2 only**. L3+ content becomes sections within L2 pages, except categories with many uniform sub-items (Workflows, CRMs, Data Objects) which get individual sub-pages.

```
docs/
├── README.md                          # Maintenance guide
├── _internal/
│   ├── feature_map.md                 # Claude nav index
│   ├── cross_ref_queue.md             # Findings about other features (forward-carry)
│   ├── blank_spots.md                 # Gaps + questions by audience
│   └── sources_scanned.md             # Already-read sources to avoid re-reading
├── getting-started/
│   ├── index.md                       # L1 landing
│   ├── platform-overview.md           # L2
│   └── quick-start.md                 # L2
├── productivity/
│   ├── index.md                       # L1 landing
│   ├── assistant.md                   # L2 — sections: onboarding, app, call, images, business cards, fair mode
│   ├── workflows/
│   │   ├── index.md                   # L2 — overview + links
│   │   ├── visit-report.md            # L3 (workflow template)
│   │   ├── call-log.md
│   │   ├── task.md
│   │   ├── email.md
│   │   ├── reminder.md
│   │   ├── meeting.md
│   │   ├── opportunity.md
│   │   ├── lead.md
│   │   ├── account.md
│   │   ├── contact.md
│   │   ├── survey.md
│   │   └── case.md
│   ├── visit-briefing.md              # L2 — sections: activity summary, (cross-selling), (order data)
│   └── customer-data-quality/
│       ├── index.md                   # L2 — overview
│       ├── lead-creation.md           # L3
│       ├── contact-creation.md
│       └── account-creation.md
├── analytics/
│   ├── index.md                       # L1 landing
│   ├── data-lake.md                   # L2 — (coming soon)
│   ├── ai-analyst.md                  # L2 — (coming soon)
│   ├── competitor-analytics.md        # L2 — live
│   ├── product-analytics.md           # L2 — (coming soon)
│   └── industry-analytics.md          # L2 — (coming soon)
├── coaching/
│   ├── index.md                       # L1 landing
│   ├── playbooks/
│   │   ├── index.md                   # L2 — overview
│   │   ├── builder.md                 # L3
│   │   └── analytics.md               # L3
│   ├── team-activity.md               # L2 — sections: activity overview, field documentation, personal profiles, (coming soon: sales productivity, pipeline creation, backoffice communication)
│   └── visit-analytics.md             # L2 — sections: live feed, visit performance, visit richness
├── platform/
│   ├── index.md                       # L1 landing
│   ├── workspace-admin.md             # L2 — sections: users, functions, assistant credits
│   ├── language-settings.md           # L2 — sections: workspace langs, assistant langs, vocabulary, translations
│   ├── security.md                    # L2 — sections: authentication (basic/oauth/sso), data processing consent
│   ├── workflow-customisation.md      # L2 — sections: overview, basic schema, parts library, workflow relations
│   ├── integrations/
│   │   ├── index.md                   # L2 — overview + CRM grid
│   │   ├── sap-c4c-v1.md             # L3 (CRM template)
│   │   ├── sap-c4c-v2.md
│   │   ├── salesforce.md
│   │   ├── ms-dynamics.md
│   │   ├── aurea.md
│   │   ├── zoho.md
│   │   └── hubspot.md
│   ├── data-objects/
│   │   ├── index.md                   # L2 — overview
│   │   ├── products.md                # L3 (data object template)
│   │   ├── competitors.md
│   │   ├── accounts.md
│   │   ├── contacts.md
│   │   ├── opportunities.md
│   │   ├── leads.md
│   │   ├── meetings.md
│   │   ├── tasks.md
│   │   └── industries.md
│   └── search-settings.md             # L2 — sections: behavior, scoring, favourites, filtering, permissions
└── bundles/
    ├── index.md                       # Bundle comparison table
    └── [10 bundle pages]
```

**Total: ~65 doc pages**

---

## Page format (Linear style)

All pages follow this master structure, grounded in Linear's actual doc patterns:

```markdown
---
status: Live | Beta | Coming soon
bundles:
  - field_sales_fundamentals
last_updated: YYYY-MM-DD
---

# Feature Name
One sentence: what it does and who it helps.

## Overview
2–3 sentences: the concept, why it exists, what it enables. No mechanics yet.

> [!NOTE]
> Available with the **[Bundle Name](../../bundles/bundle-slug.md)** bundle.

## Where to find it
"Open the VoiceLine app → tap **[Section]** → **[Feature]**."
One path per platform if they differ (mobile / web).

## [Core action or capability]
What it does. How to trigger it. **UI element names in bold**.
Cross-link inline: "VoiceLine automatically creates a [Task](../workflows/task.md) for any..."

## FAQ
**[Question]?**
Answer. Short. Honest about edge cases.
```

**Writing rules:**
- Second-person ("you"), active voice, short sentences
- Lead with **what** → then **how** (concept before mechanics)
- UI paths in bold: `**Settings → Integrations → CRM Name**`
- Bundle requirement as `[!NOTE]` callout after Overview — purchase decision, not a footnote
- Cross-links inline, never in a separate "Related" section (link first mention only)
- FAQ at end: bold question, short honest answer
- No ROI numbers, no CPO notes, no "Problems Addressed"

### Template variants

| Template | Used for | Key sections |
|----------|---------|--------------|
| **Workflow** | `workflows/*.md` (13 pages) | Overview → Where to find it → Creating a [record] → [Updating] → What syncs to CRM → FAQ |
| **CRM integration** | `integrations/*.md` (7 pages) | Overview → Where to configure it → Setup → Sync behavior (table) → Authentication → FAQ |
| **Data object** | `data-objects/*.md` (9 pages) | Overview → Where to find it → Configuration → Search behavior → FAQ |
| **Analytics** | `analytics/*.md` | Overview → Where to find it → [Key view] → Filters → FAQ |
| **Platform / config** | `platform/*.md` (L2 pages) | Overview → Where to find it → [Config topic 1] → [Config topic 2] → FAQ |
| **Coming soon** | All `()` items | 1-line intro → `[!NOTE] Coming soon` → Overview only |

---

## Source inventory

| Source | What it provides | Access |
|--------|-----------------|--------|
| This KB (`product_knowledge/`) | Feature descriptions, business context, bundle compositions | Local files |
| Strategy & vision | Tone, framing, flywheel narrative, bundle rationale | `00_strategy/product_strategy/product_strategy.md`, `00_strategy/company_vision/company_vision.md` |
| Backend (Go) | Feature scope, API surface, data models | `/Users/nicolaskubler/voiceline_repositories/voiceline_api` |
| Frontend (React) | Component names, UI labels, feature flags, screen structure | `/Users/nicolaskubler/voiceline_repositories/voiceline_frontend` |
| Mobile (Flutter) | Mobile UI flows, screen names, feature entry points | `/Users/nicolaskubler/voiceline_repositories/voiceline_flutter` |
| Notion (existing docs) | Prior customer-facing copy — partially complete | [Product Documentation](https://www.notion.so/voiceline/Product-Documentation-23ac9a7d0b41800f8cd4c995d3fdaf2b) |
| Website (voiceline.com) | Customer-language marketing copy | WebFetch |
| Figma | **Primary source for business logic** — user flows, edge case behavior, state transitions, UI labels, interaction patterns. Often contains logic not documented anywhere else. | MCP access confirmed (VoiceLine Pro). Requires file URL — see batch workflow. |
| Sales/demo decks | Customer outcome framing | TBD — flag in blank_spots.md when needed |

### Notion existing docs — coverage

| Notion page | Coverage | Maps to in new docs |
|-------------|----------|---------------------|
| [Assistant](https://www.notion.so/23ac9a7d0b4180879d5ed7260e1ca050) | Partial — conversation mode detailed; fair mode + memo mode empty | `productivity/assistant.md` |
| [Workflows](https://www.notion.so/23ac9a7d0b41804fb675cb4b516b8f86) | Sparse — only Meeting, Email, Reminder, Visit Prep have pages; Visit Report, Call Log, Task, Opp, Lead, Contact missing | `productivity/workflows/*.md` |
| [Customer Overview](https://www.notion.so/25cc9a7d0b4180caa14ff9b19789f6da) | Good — activity timeline, visit prep, conversational overview | `productivity/visit-briefing.md` |
| [Customer Search](https://www.notion.so/244c9a7d0b4180dcba68cfabe5c26e77) | Good — search mechanics, favourites, ranking, extended search, permissions | `platform/search-settings.md` + `platform/data-objects/` |
| [Integration Setup](https://www.notion.so/244c9a7d0b418009b23fd7d58915fda7) | Outline only — one CRM sub-page (C4C v1) | `platform/integrations/*.md` |
| [Administration & Security](https://www.notion.so/25bc9a7d0b418061b3edef75f2104453) | Partial — data deletion policies + org structure | `platform/workspace-admin.md`, `platform/security.md` |
| [Voice Recognition](https://www.notion.so/245c9a7d0b4180b2a1f5f2e7e5f5a2a1) | Unknown | TBD |

---

## Strategy and vision alignment

The product strategy and company vision inform the docs at two levels: **framing** (what VoiceLine is and why it matters) and **structure** (how the platform areas relate to each other).

### Key messages to carry through

| Message | Source | Where it applies |
|---------|--------|-----------------|
| "The operating system for the enterprise front line" | Company vision | Platform Overview, Getting Started |
| "We replaced the secretary that frontline workers lost" | Company vision | Platform Overview, Assistant page |
| "Doing the work and documenting the work are the same thing" | Company vision | Assistant page, Workflow overviews |
| Flywheel: capture → analyze → steer | Product strategy | Platform overview, area landing pages, bundle overview |
| FSF is the entry point; other bundles unlock specific use cases | Modularisation strategy | Getting Started > Bundles overview, every bundle page |
| Tier 1 (table stakes) → Tier 2 (differentiated) → Tier 3 (deep cross-system) | T-model | Platform overview (context), not stated explicitly in feature pages |

### Tone implications

- Frame features around what the **rep** is freed from, not what the feature technically does. "Document your visit while your mind is still on the customer" > "creates a visit report record in the CRM."
- Manager-facing features should emphasize **visibility and steering**, not reporting. "See where your team's visits are landing" > "view visit activity dashboard."
- Platform/admin features should emphasize **simplicity of setup**, not feature count. "Connect your CRM in a few steps" > "supports OAuth, Basic Auth, and SSO."
- Never describe VoiceLine as a "CRM add-on" or "voice capture tool" — it's a platform.

### Getting Started pages (specific guidance)

- **Platform Overview**: Use the vision narrative — frontline workers → lost secretary → VoiceLine restores it. Introduce the flywheel (capture → analyze → steer). Link to area landing pages.
- **Quick Start**: Practical — download app, connect CRM, create first visit report. No strategy language.

---

## Processing strategy

### Four internal working files in `docs/_internal/`

**`feature_map.md`** — master index. Columns: Feature | Area | Status | Internal KB path | Doc path | Sources ✓ | Blank spots. Seeded from hierarchy; updated per batch.

**`cross_ref_queue.md`** — findings about other features encountered during scanning. Any time a source mentions a feature not currently being processed, log it here for the next batch. Checked first at the start of every feature's research.

**`blank_spots.md`** — gaps logged continuously. Format: Feature | Gap | Audience (CPO / Dev / Designer) | Priority. Surfaced as a routable question list after each batch.

**`sources_scanned.md`** — running log of every source file/page read, what it covered, and key findings. Prevents re-reading the same backend packages, Figma files, or Notion pages for subsequent features. Format:

| Source | Type | Read during | Features covered | Key findings |
|--------|------|-------------|-----------------|--------------|
| `reports/handler.go` | Backend | Batch 1 | visit_report, task_creation | Handler L1–200 covers creation; L340 auto-creates tasks |
| Figma "Workflows Sprint 14" | Figma | Batch 1 | visit_report, opportunity | Frame list extracted; states documented |

**Research order for each feature:**
1. Check `cross_ref_queue.md` — any pre-existing findings for this feature?
2. Check `sources_scanned.md` — any already-read sources that cover this feature?
3. Only read new sources not yet in the index.

### Batch workflow (5 phases per batch)

#### Phase 0 — Figma link collection (before research starts)
Figma is a primary source for business logic — user flows, state transitions, edge cases, and UI labels that may not be documented anywhere else. The MCP requires a file URL to access it; there is no search-by-name.

Before starting research on a new batch, ask in one message:

> "Starting Batch [N]: [feature list]. Please share the Figma file URL (or frame URL) for each of these. If a feature spans multiple files/frames, share all relevant ones."

Once URLs are provided, proceed to Phase A. Features without a Figma URL get a Designer question logged in `blank_spots.md` and research continues without it.

#### Phase A — Research (no writing yet)
For each feature in the batch:
1. Read internal KB file
2. **Read Figma** — use `get_design_context` with provided URL → extract flows, states, labels, edge cases, business logic
3. Scan backend repo for handlers/models
4. Search Notion for specs, onboarding, feedback
5. Scan website for public copy
6. Cross-ref queue: log any findings about OTHER features encountered
7. Log every gap, ambiguity, or missing source to `blank_spots.md` with audience tag

#### Phase B — CPO interview (batch Q&A)
After researching ALL features in the batch, present one consolidated question list:

```
## Batch [N] — Questions before writing

### For you (CPO)
1. [Feature X] — [specific question about behavior/UX/intent]
2. [Feature Y] — [question]
...

### For devs (forward to engineering)
1. [Feature X] — Where is [handler/model] located in the codebase?
2. [Feature Y] — What does [API field] map to in the CRM sync?
...

### For designers (forward to design)
1. [Feature X] — Figma URL not provided — which file covers this?
2. [Feature Y] — What is the exact label for [element] in the UI?
...
```

Rules:
- Never write content I'm not confident about — use `[TBD: confirm X]` placeholder instead
- Questions are batched across ALL features in one message — not one message per feature
- Dev and designer questions are clearly separated so they can be forwarded without editing
- You can skip or defer any question — it stays in `blank_spots.md` for later

#### Phase C — Write
With answers in hand, write all pages for the batch. Any unanswered questions become `[TBD: ...]` placeholders in the draft.

#### Phase D — Batch review
Present a summary table, not individual pages:

```
## Batch [N] — Review

| Page | Confidence | Placeholders | Key decisions made |
|------|-----------|--------------|-------------------|
| workflows/visit-report.md | High | 0 | — |
| workflows/opportunity.md | Medium | 2 | [TBD: update flow behavior] |
| analytics/competitor-analytics.md | High | 0 | — |
```

Review options:
- **Approve all** → pages are finalized, move to next batch
- **Spot-check specific page** → open that page, review in IDE
- **Reject a section** → flag it, I'll revise before finalizing

Batch size: 5–8 pages for content-heavy sections (Workflows); up to 13 for simpler templates (Data Objects).

---

## KB features not yet in hierarchy

These internal KB features have no hierarchy placement. Most are Backlog/Planned. Flagged in `blank_spots.md`; no pages created until hierarchy is updated.

| KB feature | Status | Likely maps to |
|------------|--------|----------------|
| route_planning | Backlog | Not in hierarchy |
| territory_analytics | Backlog | Team Activity > Activity Overview? |
| territory_penetration_dashboard | Backlog | Same |
| demand_analysis | Planned | Team Activity > (Sales Productivity)? |
| demand_prediction | Planned | Same |
| potential_analysis | Planned | Same |
| update_account_potential | Backlog | Not in hierarchy |
| campaign_mapping | Backlog | Fair Mode or Integrations? |
| conversational_coaching | Backlog | Team Activity > (Sales Productivity)? |
| open_positions_overview | Planned | Team Activity > (Pipeline Creation)? |
| order_analysis | Planned | Visit Briefing > (Order Data)? |
| customer_prioritisation_* | Planned | Team Activity > (Pipeline Creation)? |

---

## Open questions

| Question | Status | Notes |
|----------|--------|-------|
| Sales/demo deck location | Low priority | Not needed for Phase 2; flag in blank_spots.md if a specific feature needs it |
| Changelog/release notes location | Low priority | Not needed for Phase 2; add to blank_spots.md |
| Hosting framework | Deferred | Docusaurus 3 (recommended) or MkDocs Material — framework-agnostic content; decide at hosting setup |
| Multi-language support | Decision needed | See section below |

### Multi-language docs

The product already supports multiple languages (the "Language Settings" platform area). The docs site will eventually need the same.

**Recommended approach for the future:**

1. **Phase 1 (now):** Write all docs in English. Content is framework-agnostic markdown — no translation infrastructure needed yet.
2. **Phase 2 (at hosting):** Choose a framework with built-in i18n. **Docusaurus 3 has native i18n support** (`i18n/` folder per locale, `docusaurus.config.js` locale config). MkDocs Material also supports it via the `mkdocs-static-i18n` plugin.
3. **Translation workflow (recommended):**
   - English as the source of truth
   - Machine translation (DeepL API or similar) generates first-pass translations per locale
   - Human review for key pages (Getting Started, Bundles) in priority markets (DE, FR, ES)
   - Docusaurus crowdin integration available for ongoing maintenance
4. **Locale candidates** (based on VoiceLine's markets): `de`, `fr`, `es`, `it`, `pl` — confirm with CPO/sales

**What this means for Phase 1:** No action needed now. Write clean, translation-friendly English — avoid idioms, keep sentences short, avoid embedded UI screenshots with text (use alt text instead). This makes machine translation cleaner.

---

## Decision log

| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-02-27 | Customer docs in `docs/` folder within this repo | Close to internal KB; extractable to separate repo for hosting later |
| 2026-02-27 | Navigate by product area, not use case | 1:N feature-to-area relationships; Linear-style product areas more natural for customers |
| 2026-02-27 | Value calculation files stay in `product_documentation/` | Internal business tools, not documentation |
| 2026-02-27 | Feature hierarchy from CPO is authoritative | KB features are neither exhaustive nor at the right abstraction level |
| 2026-02-27 | `sources.yaml` per feature folder (internal) | Single place to find a feature across all systems |
| 2026-02-27 | Linear docs as style reference | Clean, action-oriented, second-person format |
| 2026-03-02 | Sidebar = L1 + L2 only | Per hierarchy_draft.md description; L3+ content goes into page body |
| 2026-03-02 | L3 sub-pages for Workflows, CRMs, Data Objects | Uniform categories with many children warrant individual pages + templates |
| 2026-03-02 | Overview + Where to find it + Bundle callout as fixed sections | Grounded in Linear's Triage/Projects pages; bundle requirement is a purchase decision, surfaces upfront |
| 2026-03-02 | () items = Coming soon pages | Per hierarchy_draft.md description |
| 2026-03-02 | Cross-links inline only, no "Related" section | Linear pattern; inline links are more readable and contextual |
| 2026-03-02 | Strategy + vision docs inform tone and framing | Feature pages reflect the flywheel narrative and "operating system" positioning, not just technical mechanics |
| 2026-03-02 | Multi-language: English first, Docusaurus i18n + DeepL later | Framework-agnostic content now; i18n infrastructure added at hosting setup |
| 2026-03-02 | All repos at `/Users/nicolaskubler/voiceline_repositories/` | Backend (Go), Frontend (React), Mobile (Flutter) all confirmed present |
| 2026-03-02 | Figma is a primary source, not optional | Contains business logic not documented elsewhere; researched for every feature via MCP |
| 2026-03-02 | Figma links collected in Phase 0 before each batch | MCP needs URL — no search-by-name. Pre-batch collection keeps research unblocked. |
| 2026-03-02 | Batch workflow: Figma links → research → interview → write → review | CPO answers questions once per batch; questions routed by audience (CPO / Dev / Designer) |
| 2026-03-02 | Uncertain content uses `[TBD: ...]` placeholder, never fabricated | Quality gate: no invented content; blanks are visible and trackable |

---

*Last updated: 2026-03-02*
