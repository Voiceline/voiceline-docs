# CLAUDE.md — VoiceLine Docs

## What this repo is

Customer-facing and internal product documentation for VoiceLine. This repo contains **only documentation** — no code, no internal KB, no ROI calculations.

The internal knowledge base (features, value model, competitive analysis) lives separately in a Google Drive repo.

---

## Folder map

```
voiceline-docs/
├── README.md               Human-readable repo overview
├── CLAUDE.md               This file
├── CONTRIBUTING.md         Writing conventions, templates, maintenance guide
│
├── _internal/              NOT published — working files for AI agents and maintainers
│   ├── README.md           Explains each internal file
│   ├── feature_map.md      Master index: all 45+ pages with research/writing status
│   ├── blank_spots.md      Known gaps and open questions, routed by audience
│   ├── cross_ref_queue.md  Forward-carry findings across batches
│   ├── sources_scanned.md  Log of sources read (prevents re-reading)
│   ├── docs_project.md     Full project history, phases, decision log
│   ├── hierarchy_draft.md  CPO-provided feature hierarchy (authoritative)
│   └── figma_links.md      Figma URLs per feature
│
├── commercial/             Internal sales/pricing docs
│   ├── pricing-overview.mdx         Stacking model + implementation fees
│   ├── field-sales-fundamentals.mdx Base package (FSF)
│   ├── project-timeline.mdx         Stub
│   ├── modules/                     One file per add-on module
│   │   ├── index.mdx
│   │   ├── pipeline-management.mdx
│   │   ├── customer-data.mdx
│   │   ├── marketing-surveys.mdx
│   │   ├── service-cases.mdx
│   │   ├── market-analytics-pro.mdx
│   │   ├── sales-coaching-pro.mdx
│   │   ├── industry-fairs.mdx
│   │   └── inside-sales.mdx
│   └── platform/
│       ├── index.mdx
│       ├── professional.mdx
│       └── enterprise.mdx
│
├── engineering/            Developer docs (stub)
├── implementation/         Solutions Architect / delivery guides
│   ├── getting-started/    initial-setup, project-team, adding-modules, adding-user-groups
│   ├── standard-implementations/  FSF configuration — workspace, workflows, data
│   ├── workflow-customisation/    Component library and customisation
│   ├── modules/            Implementation guides per add-on module
│   ├── data-integrations/  CRM connection and data flow reference
│   └── security/           Security posture and compliance
│
└── customer/               Customer-facing product documentation
    ├── getting-started/    index.md, platform-overview.md, quick-start.md
    ├── productivity/       index.md, assistant.md, visit-briefing.md
    │   ├── workflows/      13 workflow pages (visit-report, call-log, task, email, ...)
    │   └── customer-data-quality/  3 pages (lead, contact, account creation)
    ├── analytics/          6 pages (competitor, product, industry, data-lake, ai-analyst)
    ├── coaching/           index.md, team-activity.md, visit-analytics.md
    │   └── playbooks/      index.md, builder.md, analytics.md
    └── platform/           index.md + 6 top-level pages
        ├── integrations/   8 CRM integration pages
        └── data-objects/   10 data object pages
```

---

## Navigation — start here

- **Find a feature page**: `_internal/feature_map.md` — master index of all pages with file paths and status
- **Find known gaps**: `_internal/blank_spots.md`
- **Understand a feature**: go to `customer/{area}/{feature}.md`
- **Understand pricing**: go to `commercial/`
- **Project history / decisions**: `_internal/docs_project.md`

---

## File naming and structure

- File names must match the page's displayed title in kebab-case: `title: "Adding Modules"` → `adding-modules.mdx`
- Folder names must mirror the navigation section names shown in the webapp: a page in the "Getting Started" nav group lives in a `getting-started/` subfolder
- When creating or moving pages, update `docs.json` to match and delete the old files

## Writing rules (all docs)

- **Don't duplicate information across pages.** Every fact belongs in one place. If another page needs to reference it, link to the source page — don't copy the content. This prevents the docs from diverging and means updates only ever need to happen in one place.
  - The canonical source for a topic is the page whose primary subject it is (e.g. language availability → `/customer/platform/language-settings`, CRM connection → the relevant integration page).
  - Implementation and commercial docs may summarise a concept briefly, but must link to the canonical customer doc for full detail rather than restating it.

## Writing rules (customer docs)

- Index pages are always titled `"Overview"` — never repeat the parent category name as the page title
- Second-person ("you"), active voice, short sentences
- Lead with concept before mechanics — what it is before how to use it
- UI navigation paths in bold: **Settings → Integrations → CRM Name**
- Module requirement as `<Note>` callout after `## Overview`
- Cross-links inline on first mention only — no standalone "Related" sections
- No ROI numbers, no internal framing, no CPO notes

## Writing rules (commercial docs)

- Second-person ("you"), active voice — same register as customer docs and the Linear reference style
- Every page answers: what it is → what problem it solves → what's included
- **Section headings must be descriptive** — no generic headings like "What's included", "How pricing works", "How it works", or "Overview". Name the section after what it actually covers.
- **Feature tables use two columns: `Feature | What it does`** — no Notes/Status/Docs columns
  - Feature names use the actual product name (e.g., "Account Creation", "Visit Report") — not descriptive phrases like "Create a new account by voice"
  - Link the feature name to its customer doc when one exists
  - Write one sentence (under 15 words) in the "What it does" column — this is where the behaviour is described
  - No `—` placeholders — always write a description
- `## Why it exists` section (modules only): 2–3 sentences, lead with the customer pain
- No ROI numbers — explain the value logic, not the math
- Feature flags, caveats, and status notes belong in the customer docs, not here
- Use `<Note>` (Mintlify) for dependency requirements and trial callouts — not `> [!NOTE]`

## Writing rules (implementation docs)

- Pages open with 1–2 sentences stating the problem this configuration solves and its business value — what is missing or broken without it. This comes **before** the "By the end of this page..." block.
- Then: a **"By the end of this page your FDE will have confirmed..." block** followed by 2–4 bullet points — one per concrete deliverable. Each bullet describes the output of a piece of work, not just a topic.
  - Name who confirms with whom: "with your CRM admin", "with your project lead", "with your IT team and CRM admin", or just "confirmed:" when there is no fixed counterpart.
  - Write each bullet as the deliverable itself, not as a question — e.g. "The sync filters to apply" not "Which sync filters to use".
  - The bullets are the reader's answer to: what does this page produce?
- The body of the page explains the detail needed to make those decisions — fields, options, constraints.
- **No "Scoping decisions" sections.** The opening paragraph, "By the end of this page..." block, and body together are sufficient. Never add a trailing section listing open questions.

---

## YAML frontmatter (required on every customer doc)

Do **not** include a `description` field — page descriptions are not used.

```yaml
---
status: Live | Beta | Coming soon
bundles:
  - field_sales_fundamentals   # one or more slugs
last_updated: YYYY-MM-DD
---
```

Platform pages (integrations, data objects, admin) omit the `bundles:` field.

### Bundle slugs

| Slug | Commercial page |
|------|----------------|
| `field_sales_fundamentals` | `/commercial/field-sales-fundamentals` |
| `pipeline_management` | `/commercial/modules/pipeline-management` |
| `customer_data` | `/commercial/modules/customer-data` |
| `marketing_surveys` | `/commercial/modules/marketing-surveys` |
| `service_cases` | `/commercial/modules/service-cases` |
| `market_analytics_pro` | `/commercial/modules/market-analytics-pro` |
| `sales_coaching_pro` | `/commercial/modules/sales-coaching-pro` |
| `industry_fairs` | `/commercial/modules/industry-fairs` |

---

## Cross-reference paths

All links use **absolute paths without file extensions** (Mintlify convention).

| From | To | Pattern |
|------|----|---------|
| `customer/X/page.mdx` | Another customer page | `/customer/area/page` |
| `customer/X/page.mdx` | Commercial page | `/commercial/modules/page` |
| `commercial/page.mdx` | Customer page | `/customer/area/page` |

---

## What NOT to put here

- Internal KB content (feature specs, problems, use cases from product_documentation/)
- ROI calculations or value model numbers
- CPO interview notes or assumption tags
- Anything from value_proposition/, gtm_communications/, or competitors_knowledge/
