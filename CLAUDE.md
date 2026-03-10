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
│   ├── index.md            Bundle overview table with pricing
│   ├── field-sales-fundamentals.md
│   ├── modules.md
│   └── platform.md
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
- Module requirement as `[!NOTE]` callout after `## Overview`
- Cross-links inline on first mention only — no standalone "Related" sections
- No ROI numbers, no internal framing, no CPO notes

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
| `field_sales_fundamentals` | `commercial/field-sales-fundamentals.md` |
| `pipeline_management` | `commercial/modules.md#pipeline-management` |
| `customer_data` | `commercial/modules.md#customer-data` |
| `marketing_surveys` | `commercial/modules.md#marketing-surveys` |
| `service_cases` | `commercial/modules.md#service-cases` |
| `market_analytics_pro` | `commercial/modules.md#market-analytics-pro` |
| `sales_coaching_pro` | `commercial/modules.md#sales-coaching-pro` |
| `industry_fairs` | `commercial/modules.md#industry-fairs` |

---

## Cross-reference paths

All links use relative paths.

| From | To | Pattern |
|------|----|---------|
| `customer/X/page.md` | Another customer page | `../other-page.md` or `../../area/page.md` |
| `customer/X/page.md` | Commercial page | `../../commercial/modules.md#anchor` |
| `commercial/page.md` | Customer page | `../customer/area/page.md` |

---

## What NOT to put here

- Internal KB content (feature specs, problems, use cases from product_documentation/)
- ROI calculations or value model numbers
- CPO interview notes or assumption tags
- Anything from value_proposition/, gtm_communications/, or competitors_knowledge/
