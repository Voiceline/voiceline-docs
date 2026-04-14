# Feature Freeze SOT — Progress Tracker

Last updated: 2026-04-04

## Legend
- ✅ Complete
- 🔄 In progress
- 📋 Stubbed (structure created, content needs filling)
- ❌ Not started
- ⚠️ Blocked (needs input — see notes)

---

## Phase 1 — Project Scaffolding ✅

| File | Status | Notes |
|------|--------|-------|
| `_internal/projects/feature-freeze-sot/README.md` | ✅ | |
| `_internal/projects/feature-freeze-sot/progress.md` | ✅ | This file |
| `_internal/projects/feature-freeze-sot/external_knowledge_index.md` | ✅ | Backend repo path for standard impls TBD |

---

## Phase 2 — Modules & Pricing ✅

| File | Status | Notes |
|------|--------|-------|
| `commercial/index.mdx` | ✅ | Created — landing page for Modules & Pricing tab |
| `commercial/how-modules-work.mdx` | ✅ | Created — FSF-first model, 90-day rule, sequential expansion |
| `commercial/field-sales-fundamentals.mdx` | ✅ | Existing — framing reviewed, no changes needed |
| `commercial/modules/index.mdx` | ✅ | Existing — framing reviewed |
| `commercial/modules/market-analytics-pro.mdx` | ✅ | Existing |
| `commercial/modules/sales-coaching-pro.mdx` | ✅ | Existing |
| `commercial/modules/pipeline-management.mdx` | ✅ | Existing |
| `commercial/modules/customer-data.mdx` | ✅ | Existing |
| `commercial/modules/marketing-surveys.mdx` | ✅ | Existing |
| `commercial/modules/service-cases.mdx` | ✅ | Existing |
| `commercial/modules/industry-fairs.mdx` | ✅ | Existing |
| `commercial/modules/inside-sales.mdx` | ✅ | Existing |

---

## Phase 3 — Implementation Section ✅

### Our Approach (entry point)
| File | Status | Notes |
|------|--------|-------|
| `implementation/index.mdx` | ✅ | Philosophy overview, navigation CTA |
| `implementation/our-approach/phase-1-fsf.mdx` | ✅ | 90-day rule, explicitly stated |
| `implementation/our-approach/phase-2-expansion.mdx` | ✅ | Module rollout after day 90 |
| `implementation/our-approach/example-timelines.mdx` | ✅ | 4 reference timeline patterns |

### Standard Implementations
| File | Status | Notes |
|------|--------|-------|
| `implementation/standard-implementations/index.mdx` | ✅ | Overview + workflow table |
| `implementation/standard-implementations/visit-report.mdx` | ✅ | CRM-agnostic draft — needs engineering review |
| `implementation/standard-implementations/call-log.mdx` | ✅ | CRM-agnostic draft |
| `implementation/standard-implementations/task.mdx` | ✅ | CRM-agnostic draft |
| `implementation/standard-implementations/email.mdx` | ✅ | CRM-agnostic draft |
| `implementation/standard-implementations/meeting.mdx` | ✅ | CRM-agnostic draft |
| `implementation/standard-implementations/opportunity.mdx` | ✅ | CRM-agnostic draft |
| `implementation/standard-implementations/lead.mdx` | ✅ | CRM-agnostic draft |
| `implementation/standard-implementations/contact.mdx` | ✅ | CRM-agnostic draft |
| `implementation/standard-implementations/account.mdx` | ✅ | CRM-agnostic draft |
| `implementation/standard-implementations/reminder.mdx` | ✅ | CRM-agnostic draft |

### Product Customisation
| File | Status | Notes |
|------|--------|-------|
| `implementation/product-customisation/index.mdx` | ✅ | Component model + evaluation criteria |
| `implementation/product-customisation/component-library.mdx` | ✅ | Full 57-component catalogue extracted from vl-tools.com API — needs SA review |
| `implementation/product-customisation/requesting-customisation.mdx` | ✅ | ROI + carry-over criteria, process |

### Data & Integrations
| File | Status | Notes |
|------|--------|-------|
| `implementation/data-integrations/index.mdx` | ✅ | CRM-agnostic sync model, retention table |

### Security & Compliance
| File | Status | Notes |
|------|--------|-------|
| `implementation/security/index.mdx` | ✅ | Summary + trust.voiceline.ai pointer; SA section stubbed |

---

## Phase 4 — Integrations Tab ✅

### Overview
| File | Status | Notes |
|------|--------|-------|
| `integrations/index.mdx` | ✅ | |

### SAP C4C v1 (priority)
| File | Status | Notes |
|------|--------|-------|
| `integrations/sap-c4c-v1/index.mdx` | ✅ | Setup & auth |
| `integrations/sap-c4c-v1/data-sync.mdx` | ✅ | Field mappings drafted — needs engineering review |
| `integrations/sap-c4c-v1/standard-implementation.mdx` | ✅ | Scoping decisions + go-live checklist |

### Salesforce (priority)
| File | Status | Notes |
|------|--------|-------|
| `integrations/salesforce/index.mdx` | ✅ | Setup & auth |
| `integrations/salesforce/data-sync.mdx` | ✅ | Field mappings drafted — needs engineering review |
| `integrations/salesforce/standard-implementation.mdx` | ✅ | Scoping decisions + go-live checklist |

### SAP C4C v2
| File | Status | Notes |
|------|--------|-------|
| `integrations/sap-c4c-v2/index.mdx` | ✅ | |
| `integrations/sap-c4c-v2/data-sync.mdx` | ✅ | Field-level mappings from backend repo |
| `integrations/sap-c4c-v2/standard-implementation.mdx` | ✅ | Scoping decisions + go-live checklist complete |

### MS Dynamics 365
| File | Status | Notes |
|------|--------|-------|
| `integrations/ms-dynamics/index.mdx` | ✅ | |
| `integrations/ms-dynamics/data-sync.mdx` | ✅ | Field-level mappings from backend repo |
| `integrations/ms-dynamics/standard-implementation.mdx` | ✅ | Scoping decisions + go-live checklist complete |

### HubSpot
| File | Status | Notes |
|------|--------|-------|
| `integrations/hubspot/index.mdx` | ✅ | |
| `integrations/hubspot/data-sync.mdx` | ✅ | Field-level mappings from backend repo |
| `integrations/hubspot/standard-implementation.mdx` | ✅ | Scoping decisions + go-live checklist complete |

### ZOHO CRM
| File | Status | Notes |
|------|--------|-------|
| `integrations/zoho/index.mdx` | ✅ | |
| `integrations/zoho/data-sync.mdx` | ✅ | Field-level mappings from backend repo |
| `integrations/zoho/standard-implementation.mdx` | ✅ | Scoping decisions + go-live checklist complete |

### Aurea CRM
| File | Status | Notes |
|------|--------|-------|
| `integrations/aurea/index.mdx` | ✅ | |
| `integrations/aurea/data-sync.mdx` | ✅ | Field-level mappings from backend repo |
| `integrations/aurea/standard-implementation.mdx` | ✅ | Scoping decisions + go-live checklist complete |

---

## Phase 5 — Product Docs Callouts ✅

| Workflow | Callout added | Notes |
|----------|--------------|-------|
| `customer/productivity/workflows/visit-report.mdx` | ✅ | |
| `customer/productivity/workflows/call-log.mdx` | ✅ | |
| `customer/productivity/workflows/task.mdx` | ✅ | |
| `customer/productivity/workflows/email.mdx` | ✅ | |
| `customer/productivity/workflows/meeting.mdx` | ✅ | Also fixed TBD recurring meetings answer |
| `customer/productivity/workflows/opportunity.mdx` | ✅ | |
| `customer/productivity/workflows/lead.mdx` | ✅ | |
| `customer/productivity/workflows/contact.mdx` | ✅ | |
| `customer/productivity/workflows/account.mdx` | ✅ | |
| `customer/productivity/workflows/reminder.mdx` | ✅ | |
| `customer/productivity/workflows/survey.mdx` | ✅ | Links to Marketing Surveys module |
| `customer/productivity/workflows/case.mdx` | ✅ | Links to Service Cases module |

---

## Phase 6 — docs.json Navigation ✅

| Task | Status | Notes |
|------|--------|-------|
| Rename "Commercials" → "Modules & Pricing" | ✅ | |
| Add "Product" tab (renamed from "Product Documentation") | ✅ | |
| Add `how-modules-work` + `commercial/index` to Modules & Pricing | ✅ | |
| Remove Integrations group from Product tab | ✅ | |
| Build out Implementation tab with all sub-sections | ✅ | |
| Add Integrations tab with all 7 CRMs × 3 pages | ✅ | |

---

## Open items requiring external input

| Item | Needed from | Priority | Status |
|------|-------------|----------|--------|
| Engineering review of standard implementation field mappings | Engineering | Medium | ⚠️ Sourced from backend repo — spot-check recommended |
| Field-level data sync mappings for SAP v2, Dynamics, HubSpot, ZOHO, Aurea | Engineering | — | ✅ Sourced from backend repo (`/crm/` folder) |
| Component library content review (vl-tools.com) | SA team | Low | ✅ vl-tools.com is SOT — no review needed |
| Backend repo path for standard implementation specs | Engineering | Medium | ⚠️ TBD |
| Customisation evaluation criteria (precise language sign-off) | Lino | Medium | ⚠️ Pending |
| SA section in Security & Compliance (recurring questions) | SA team | Low | ⚠️ Pending |
