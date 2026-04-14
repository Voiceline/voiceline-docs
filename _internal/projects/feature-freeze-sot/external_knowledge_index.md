# External Knowledge Index

This file maps all external resources referenced in or relevant to the VoiceLine documentation project. Use it as a starting point when updating any section — check here before searching elsewhere.

---

## Product Strategy

| Resource | Path | Purpose |
|----------|------|---------|
| Product Strategy (main doc) | `GoogleDrive/Shared drives/VoiceLine/6 Product/product_knowledge/00_strategy/product_strategy/product_strategy.md` | T-model framework, three strategic bets, FSF rationale, resource allocation |
| Modular Delivery Proposal (Max) | `GoogleDrive/Shared drives/VoiceLine/6 Product/product_knowledge/00_strategy/product_strategy/input/Max Modular Delivery Proposal.md` | Operational foundation for 90-day FSF rule, POC model, sequential module rollout |
| Strategy Tracker | `GoogleDrive/Shared drives/VoiceLine/6 Product/product_knowledge/00_strategy/strategy_project.md` | Phase progress, key decisions log |
| Company Vision | `GoogleDrive/Shared drives/VoiceLine/6 Product/product_knowledge/00_strategy/company_vision/` | Mission, vision, core beliefs |

**Google Drive base path:** `/Users/nicolaskubler/Library/CloudStorage/GoogleDrive-lino@getvoiceline.com/Shared drives/VoiceLine/6 Product/product_knowledge/`

---

## Product Documentation KB

| Resource | Path | Purpose |
|----------|------|---------|
| Feature index (56 features) | `...product_knowledge/product_documentation/00_meta/index.md` | All features by use case, with status |
| Feature docs (per feature) | `...product_knowledge/product_documentation/01_features/` | Deep feature specs, customer evidence, value chain |
| Playbooks feature doc | `...product_documentation/01_features/playbooks/playbooks.md` | Baseline workflows, coaching mechanics |

---

## GTM & Pricing

| Resource | Path | Purpose |
|----------|------|---------|
| GTM index | `...product_knowledge/gtm_communications/00_meta/index.md` | 8 core use cases, bundle mapping |
| Field Sales Fundamentals bundle | `...product_knowledge/gtm_communications/02_pricing_bundles/field_sales_fundamentals/field_sales_fundamentals.md` | FSF feature list and pricing logic |
| All bundle definitions | `...product_knowledge/gtm_communications/02_pricing_bundles/` | All module bundle definitions |

---

## Implementation & Engineering

| Resource | Location | Purpose | Access |
|----------|----------|---------|--------|
| Component library | https://vl-tools.com/component-docs | Full SA component catalogue — what can be configured per workflow | Auth required: user `Solkey`, pass `.65JL>@nEugB5?]dw%%jG#j.%!PB#6D` |
| Backend repo — CRM integrations | `/Users/nicolaskubler/voiceline_repositories/voiceline_api/crm/` | Field-level mappings per CRM: `sap/v1/`, `sap/v2/`, `salesforce/`, `dynamics/`, `hubspot/`, `zoho/`, `aurea/` | Local clone |
| Figma designs (per feature) | `_internal/figma_links.md` (this repo) | UI reference per feature | Figma account access |

---

## Security & Compliance

| Resource | Location | Purpose |
|----------|----------|---------|
| Vanta Trust Centre | https://trust.voiceline.ai/ | Certifications, SOC 2, pen test reports, DPA — authoritative source |
| Security page (product docs) | `customer/platform/security.mdx` (this repo) | Customer-facing auth & SSO docs |

---

## Internal Docs (this repo)

| Resource | Path | Purpose |
|----------|------|---------|
| Feature map | `_internal/feature_map.md` | Master index of all 45+ pages with research/writing status |
| Blank spots | `_internal/blank_spots.md` | Open questions by audience |
| Hierarchy draft | `_internal/hierarchy_draft.md` | CPO-provided product hierarchy (authoritative) |
| CONTRIBUTING.md | `CONTRIBUTING.md` | Writing conventions, YAML schema, page templates |
| docs.json | `docs.json` | Mintlify navigation config |

---

## Notes for future editors

- Google Drive files can be read directly at the file system path above (requires Drive mounted)
- vl-tools.com/component-docs requires manual copy — WebFetch cannot authenticate
- Backend repo CRM integrations are at `/Users/nicolaskubler/voiceline_repositories/voiceline_api/crm/` — one subfolder per CRM
- When adding new resources, add a row to the relevant table above
