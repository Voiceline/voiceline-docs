# Plan: Feature Freeze SOT — Implementation Tab Restructure

## Context

VoiceLine docs are the single source of truth for what sales can sell and what SAs can configure. All tabs are access-controlled. The Implementation tab is the core deliverable — it defines the rollout process, what gets configured, and what customisation is in scope.

This plan reflects the agreed final structure after several rounds of restructuring. Phases 1–6 (scaffolding, commercial tab, integrations tab, product doc callouts, navigation) are complete. This plan covers the remaining restructure of the Implementation tab.

---

## Final Navigation Structure — Implementation Tab

```
Implementation
│
├── Getting Started                          ← EXISTS (rename from "Our Approach" ✅ done)
│   ├── Overview (implementation/index)      ← EXISTS ✅
│   ├── Phase 1 — FSF Rollout               ← EXISTS ✅
│   ├── Phase 2 — Module Expansion          ← EXISTS ✅
│   └── Example Timelines                   ← EXISTS ✅
│
├── Field Sales Fundamentals                 ← EXISTS (group rename ✅ done)
│   ├── Overview                             ← EXISTS ✅
│   ├── Workspace Setup                      ← SUB-GROUP, all NEW
│   │   ├── Overview                         ← NEW
│   │   ├── Admin & Security                 ← NEW
│   │   ├── Languages & Voice Recognition    ← NEW
│   │   └── CRM Data Objects                 ← NEW
│   ├── Visit Report                         ← EXISTS ✅
│   ├── Call Log                             ← EXISTS ✅
│   ├── Task                                 ← EXISTS ✅
│   ├── Email                                ← EXISTS ✅
│   ├── Meeting                              ← EXISTS ✅
│   ├── Reminder                             ← EXISTS ✅
│   ├── Visit Preparation                    ← NEW
│   ├── Product Data                         ← NEW
│   └── Competitor Data                      ← NEW
│
├── Modules                                  ← EXISTS ✅
│   ├── Overview                             ← EXISTS ✅
│   │
│   ├── Pipeline Management                  ← index moved ✅
│   │   ├── Create Opportunity               ← file moved ✅ (title update pending)
│   │   └── Update Opportunity               ← NEW
│   │
│   ├── Customer Data                        ← index moved ✅
│   │   ├── Create Lead                      ← file moved ✅ (title update pending)
│   │   ├── Create Contact                   ← file moved ✅ (title update pending)
│   │   ├── Update Contact                   ← NEW
│   │   ├── Create Account                   ← file moved ✅ (title update pending)
│   │   └── Update Account                   ← NEW
│   │
│   ├── Marketing Surveys                    ← EXISTS ✅
│   ├── Service Cases                        ← EXISTS ✅
│   ├── Market Analytics Pro                 ← EXISTS ✅
│   ├── Sales Coaching Pro                   ← EXISTS ✅
│   │
│   ├── Industry Fairs                       ← index moved ✅
│   │   ├── Fair Report                      ← NEW
│   │   └── Lead Tracking                    ← NEW
│   │
│   └── Inside Sales                         ← EXISTS ✅
│
├── Workflow Customisation                   ← RENAME from "Product Customisation" (pending)
│   ├── Overview                             ← EXISTS as workflow-customisation.mdx → index (pending)
│   ├── Text Fields                          ← EXISTS ✅
│   ├── Selections                           ← EXISTS ✅
│   ├── CRM Lookups                          ← EXISTS ✅
│   ├── Dates & Numbers                      ← EXISTS ✅
│   ├── Summaries & AI                       ← EXISTS ✅
│   ├── Structured Data                      ← EXISTS ✅
│   └── Additional Customisation             ← RENAME from requesting-customisation (pending)
│
├── Data & Integrations                      ← EXISTS ✅
│
└── Security & Compliance                    ← EXISTS ✅
```

---

## Execution Status

### Step 1 — Move workflow pages out of FSF into Modules ✅ DONE

File moves completed via bash:

| Was | Now |
|---|---|
| `modules/pipeline-management.mdx` | `modules/pipeline-management/index.mdx` |
| `modules/customer-data.mdx` | `modules/customer-data/index.mdx` |
| `modules/industry-fairs.mdx` | `modules/industry-fairs/index.mdx` |
| `standard-implementations/opportunity.mdx` | `modules/pipeline-management/create-opportunity.mdx` |
| `standard-implementations/lead.mdx` | `modules/customer-data/create-lead.mdx` |
| `standard-implementations/contact.mdx` | `modules/customer-data/create-contact.mdx` |
| `standard-implementations/account.mdx` | `modules/customer-data/create-account.mdx` |

Remaining for Step 1: update frontmatter titles on moved files (`"Opportunity"` → `"Create Opportunity"`, etc.).

---

### Step 2 — Create new FSF pages (PENDING — awaiting confirmation)

**Workspace Setup sub-group** — `implementation/standard-implementations/workspace-setup/`

| File | Content summary |
|------|----------------|
| `index.mdx` | The scoping audit process: what gets decided before rollout begins; how the configuration document works; what to expect from the kickoff workshop |
| `admin-security.mdx` | Auth method (basic vs SSO), OAuth CRM connection, VPN requirements, MDM, CRM record access permissions, attachment handling, sync cadence |
| `languages.mdx` | Workspace default language, interface/recording/output language config, AI language detection, behaviour when recording language isn't in the output set |
| `crm-data-objects.mdx` | What VoiceLine reads from the CRM: accounts, contacts, leads, opportunities, products, competitors, users; sync cadence; how account scope per rep is configured |

**Standalone FSF pages**

| File | Content summary |
|------|----------------|
| `visit-preparation.mdx` | Brief entry — what Visit Prep does (links to product doc), no config available, callout to contact SA if additional data sources or context are needed |
| `product-data.mdx` | How to upload product catalogue for AI recognition: upload template, required fields (name, synonyms, identifiers), how AI uses this data in workflows |
| `competitor-data.mdx` | How to configure competitor tracking: upload template, what gets detected, how competitor mentions surface in visit reports and analytics |

---

### Step 3 — Create new Module pages (PENDING — awaiting confirmation)

| File | Content summary |
|------|----------------|
| `modules/pipeline-management/update-opportunity.mdx` | Standard schema for Update Opportunity (stage, probability, close date, volume); how it differs from Create Opportunity; AI record-matching logic |
| `modules/customer-data/update-contact.mdx` | Standard schema for updating an existing contact; AI match logic; which fields can be updated; deduplication |
| `modules/customer-data/update-account.mdx` | Same for accounts |
| `modules/industry-fairs/fair-report.mdx` | Fair Report workflow schema; how it differs from a standard visit report; how fair entries link to leads/contacts |
| `modules/industry-fairs/lead-tracking.mdx` | Two approaches: (1) CRM campaign sync — Salesforce only: campaigns synced with type=Event and status=Planned/In Progress, lead/contact linked as CampaignMember; (2) text/select source field — stamped on all fair entries, CRM-agnostic, no campaign object required |

---

### Step 4 — Restructure Workflow Customisation (PENDING — awaiting confirmation)

File moves:

| Was | Now |
|---|---|
| `product-customisation/workflow-customisation.mdx` | `workflow-customisation/index.mdx` |
| `product-customisation/requesting-customisation.mdx` | `workflow-customisation/additional-customisation.mdx` |
| `product-customisation/component-library.mdx` | `workflow-customisation/component-library.mdx` |
| `product-customisation/components/text-fields.mdx` | `workflow-customisation/components/text-fields.mdx` |
| `product-customisation/components/selections.mdx` | `workflow-customisation/components/selections.mdx` |
| `product-customisation/components/crm-lookups.mdx` | `workflow-customisation/components/crm-lookups.mdx` |
| `product-customisation/components/dates-numbers.mdx` | `workflow-customisation/components/dates-numbers.mdx` |
| `product-customisation/components/summaries.mdx` | `workflow-customisation/components/summaries.mdx` |
| `product-customisation/components/structured-data.mdx` | `workflow-customisation/components/structured-data.mdx` |
| `product-customisation/index.mdx` | DELETE (content absorbed into new index) |

---

### Step 5 — Update docs.json (PENDING)

Full Implementation tab nav update reflecting all moves, new pages, and sub-groups from Steps 1–4. No content writing — nav only.

---

## What does NOT change

- `Getting Started` group — complete, no changes
- `Marketing Surveys`, `Service Cases`, `Market Analytics Pro`, `Sales Coaching Pro`, `Inside Sales` — flat module pages, complete
- `Data & Integrations` — complete
- `Security & Compliance` — complete
- All `integrations/` tab pages — complete
- All `customer/` product docs — complete

---

## Open items

| Item | Status |
|------|--------|
| Update Opportunity schema — confirm fields with product | ⚠️ Draft from PDF; needs review |
| Update Contact / Update Account — confirm scope of updatable fields | ⚠️ To draft; no backend spec found yet |
| Product data upload template — confirm current format | ⚠️ Reference `_internal/` or ask SA |
| Fair Report schema — confirm from backend repo or PDF | ⚠️ PDF has schema; SAP v1 custom func found in repo |
| Lead Tracking — confirm which CRMs support campaign sync beyond Salesforce | ⚠️ Only SF found in repo so far |
| Workspace Setup — confirm standard sync cadence values | ⚠️ Draft from PDF; needs engineering confirmation |
