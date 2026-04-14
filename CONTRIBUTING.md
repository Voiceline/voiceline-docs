# VoiceLine Docs — Maintenance Guide

## Overview

The `docs/` folder contains all VoiceLine documentation — customer-facing, commercial/pricing, implementation, and engineering. It lives alongside the internal product knowledge base (`product_documentation/`, `gtm_communications/`, etc.) in the same repository.

The internal KB is **not changing**. This is a separate layer on top.

---

## Folder structure

| Folder | Audience | Contents |
|--------|----------|---------|
| `customer/` | Customers & prospects | Feature docs — what each capability does and how to use it |
| `commercial/` | Internal (sales, CS) | Module and pricing documentation — links from customer docs |
| `implementation/` | Solutions Architects, Delivery tribe | Setup and implementation guides per module |
| `engineering/` | Developers | Technical codebase documentation |
| `_internal/` | Claude / internal only | Working files — not published |

### `customer/` structure

| Subfolder | Contents |
|-----------|---------|
| `getting-started/` | Platform overview, quick start |
| `productivity/` | Assistant, Workflows, Visit Briefing, Customer Data Quality |
| `analytics/` | Data Lake, Competitor/Product/Industry Analytics, AI Analyst |
| `coaching/` | Playbooks, Team Activity, Visit Analytics |
| `platform/` | Workspace admin, integrations, data objects, language, security, search, workflow customisation |

### `implementation/` structure

| Subfolder | Contents |
|-----------|---------|
| `getting-started/` | Initial Setup, Project Team, Adding Modules, Expanding to New User Groups |
| `standard-implementations/` | FSF configuration guide — workspace setup, workflows, data |
| `workflow-customisation/` | Component library and customisation options |
| `modules/` | Implementation guides per add-on module |
| `data-integrations/` | CRM connection and data flow reference |
| `security/` | Security posture and compliance |

### `commercial/` structure

| Folder / File | Contents |
|--------------|---------|
| `index.mdx` | Overview — package structure and entry points |
| `field-sales-fundamentals/` | FSF base package — split into index, productivity, market-analytics, sales-coaching |
| `credits/` | AI credit system — index, packages, consumption |
| `modules/` | One file per add-on module |
| `platform/` | Professional and Enterprise platform tiers |
| `pricing-scenarios/` | Example customer configurations (small, medium, enterprise) |

### `_internal/` files (not published)

| File | Purpose |
|------|---------|
| `feature_map.md` | Master index — tracks all pages with file paths and status |
| `docs_hidden_nav.json` | Navigation sections removed from docs.json pending completion — re-add when ready |
| `cross_ref_queue.md` | Incidental findings about other features (forward-carry between batches) |
| `blank_spots.md` | Gaps, questions, and missing sources — routed by audience |
| `sources_scanned.md` | Log of every source file/page read — prevents re-reading |

---

## Writing conventions (customer docs)

- Second-person ("you"), active voice, short sentences
- Lead with **what it is** before **how to use it** — concept before mechanics
- UI paths in bold: **Settings → Integrations → CRM Name**
- Module requirement as `<Note>` callout immediately after `## Overview`
- Cross-links inline on first mention only — no standalone "Related" sections
- No ROI numbers, no internal framing, no CPO notes

---

## Writing conventions (implementation docs)

Implementation docs (`implementation/`) are for Solutions Architects and Forward Deployed Engineers. They describe exactly what gets configured, in what order, and what decisions the team needs to make at each step.

### Page structure

Every configuration page follows this structure:

1. **Opening paragraph** — 1–2 sentences stating the problem this configuration solves and its business value: what is missing or broken without it. This comes **before** the "By the end..." block.
2. **"By the end of this page your FDE will have confirmed..." block** — 2–4 bullet points, one per concrete deliverable. Each bullet describes the output of a piece of work, not just a topic.
3. **Body sections** — the detail needed to make those decisions: fields, options, constraints.

**Rules for the "By the end..." block:**
- Name who confirms with whom: "with your CRM admin", "with your project lead", "with your IT team and CRM admin", or just "confirmed:" when there is no fixed counterpart.
- Write each bullet as the deliverable itself, not as a question — e.g. "The sync filters to apply" not "Which sync filters to use".
- No trailing "Scoping decisions" sections — the opening paragraph, block, and body together are sufficient.

---

## Writing conventions (commercial docs)

Commercial docs (`commercial/`) explain what's in each package, why it exists, and what value it creates. Write in second-person ("you"), active voice — the same register as customer docs and the Linear reference style.

### Page structure

Every commercial page follows this structure:

1. **YAML frontmatter** — `title`, `status`, `last_updated` (and `price_per_user_month` for FSF)
2. **Price callout** — `> **€X / month**` immediately under frontmatter
3. **One-paragraph summary** — what the package/module is in plain language
4. **Why it exists** (modules only) — the problem it solves and the value logic. Two to three sentences. Lead with the customer pain, then explain how the module addresses it. No ROI numbers — explain the logic, not the math.
5. **Feature sections** — one `###` section per feature group, each with:

**Section heading rules:** Headings must be descriptive — name the section after what it actually covers. Avoid generic headings like "What's included", "How pricing works", "How it works", or "Overview".
   - A short description (1–2 sentences) of what the feature set does
   - A `Feature | What it does` table (see below)
   - An optional `→ [Section docs](/path)` link for the overview page

### Feature table format

Use a two-column table. The first column names the feature (with an optional hyperlink to its customer doc). The second column gives a one-liner explanation of what the feature does.

```markdown
| Feature | What it does |
|---------|-------------|
| [Feature name](/customer/area/page) | One sentence describing what it does for the user |
| Feature without a doc yet | One sentence describing what it does |
```

**Rules:**
- No "Notes", "Status", or "Docs" columns — feature flags and caveats belong in the source customer docs, not here
- No `—` placeholders — if there's no doc, omit the link; always write a description
- Keep descriptions to one sentence — under 15 words
- Link to the most specific customer doc available; link to section overviews only when no specific page exists

### Callout usage

Use `<Note>` (Mintlify component) for:
- Module dependency requirements (e.g. requires FSF to be live)
- Trial period inclusions (e.g. 1-month free trial)
- Coming soon status notices

Do not use `> [!NOTE]` (GitHub markdown) — this is a Mintlify project.

### File naming convention

File names must match the page's displayed title, converted to kebab-case. The folder structure must mirror the navigation sections shown in the webapp.

**Rules:**
- `title: "Adding Modules"` → filename `adding-modules.mdx` ✓
- `title: "Adding Modules"` → filename `how-we-work.mdx` ✗
- A page inside the "Getting Started" nav section → file lives in a `getting-started/` subfolder ✓
- A page inside the "Getting Started" nav section → file lives in `our-approach/` ✗

When renaming or moving pages, update `docs.json` to match and remove the old files.

### Links

All links use absolute paths without file extensions:
- ✓ `/customer/productivity/assistant`
- ✗ `../customer/productivity/assistant.md`

Cross-references to other commercial pages:
- ✓ `/commercial/modules/market-analytics-pro`
- ✗ `modules.md#market-analytics-pro`

---

## YAML frontmatter

Required on every customer doc page:

```yaml
---
status: Live | Beta | Coming soon
bundles:
  - field_sales_fundamentals
last_updated: YYYY-MM-DD
---
```

### Module slugs

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

Platform pages (integrations, data objects, admin, security, etc.) do not carry a `bundles:` field.

### Status values

| Value | Meaning |
|-------|---------|
| `Live` | Generally available |
| `Beta` | Working but not officially released |
| `Coming soon` | Not yet available — page is a placeholder |

---

## Adding a new feature page

1. Create the `.md` file in the relevant `customer/` subfolder
2. Add YAML frontmatter (`status`, `bundles`, `last_updated`)
3. Follow the template for the page type (see `docs_project.md` → "Page format")
4. Add a `<Note>` callout linking to the relevant `commercial/` page
5. Update `_internal/feature_map.md`

## Updating a commercial page

When pricing or module contents change, update `commercial/field-sales-fundamentals.md`, `commercial/modules.md`, or `commercial/platform.md` directly. The source of truth for commercial content is the Notion [Modules Documentation](https://www.notion.so/voiceline/Modules-Documentation-31ac9a7d0b418016b7e4f1d8364f56db) page.

## Page templates

| Template | Used for |
|----------|---------|
| Workflow | `productivity/workflows/*.md` |
| CRM integration | `platform/integrations/*.md` |
| Data object | `platform/data-objects/*.md` |
| Analytics | `analytics/*.md` |
| Platform / config | L2 pages in `platform/`, `productivity/`, `coaching/` |
| Coming soon | Features not yet available |

Full template examples: see `docs_project.md` → "Page format (Linear style)".

---

*Last updated: 2026-03-09*
