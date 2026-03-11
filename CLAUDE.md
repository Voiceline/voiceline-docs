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
├── implementation/         Solutions Architect guides (stub)
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

## Writing rules (customer docs)

- Second-person ("you"), active voice, short sentences
- Lead with concept before mechanics — what it is before how to use it
- UI navigation paths in bold: **Settings → Integrations → CRM Name**
- Module requirement as `<Note>` callout after `## Overview`
- Cross-links inline on first mention only — no standalone "Related" sections
- No ROI numbers, no internal framing, no CPO notes

## Writing rules (commercial docs)

- Active voice, third-person or neutral — these are internal reference pages, not instructions
- Every page answers: what it is → what problem it solves → what's included
- **Feature tables use two columns: `Feature | What it does`** — no Notes/Status/Docs columns
  - Link the feature name to its customer doc when one exists
  - Write one sentence (under 15 words) in the "What it does" column
  - No `—` placeholders — always write a description
- `## Why it exists` section (modules only): 2–3 sentences, lead with the customer pain
- No ROI numbers — explain the value logic, not the math
- Feature flags, caveats, and status notes belong in the customer docs, not here
- Use `<Note>` (Mintlify) for dependency requirements and trial callouts — not `> [!NOTE]`

---

## YAML frontmatter (required on every customer doc)

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
