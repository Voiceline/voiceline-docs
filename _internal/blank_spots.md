# Blank Spots

Gaps, ambiguities, and open questions discovered during research. Updated per batch.

**Audience tags**: CPO (product/UX decisions) | Dev (codebase questions) | Designer (Figma/UI questions)
**Priority**: High (blocks writing) | Medium (affects quality) | Low (nice to have)

---

## Open

### Pre-seeded: KB features not in docs hierarchy

These internal KB features have no placement in the docs hierarchy. No pages created until hierarchy is updated.

| Feature | Gap | Audience | Priority |
|---------|-----|----------|---------|
| `route_planning` | Not in docs hierarchy — should it be documented? | CPO | Low |
| `territory_analytics` | Not in hierarchy — possibly Team Activity > Activity Overview? | CPO | Low |
| `territory_penetration_dashboard` | Not in hierarchy — same as above | CPO | Low |
| `demand_analysis` | Not in hierarchy — possibly Team Activity > (Sales Productivity)? | CPO | Low |
| `demand_prediction` | Not in hierarchy — same as above | CPO | Low |
| `potential_analysis` | Not in hierarchy — same as above | CPO | Low |
| `update_account_potential` | Not in hierarchy — no obvious placement | CPO | Low |
| `campaign_mapping` | Not in hierarchy — possibly Fair Mode or Integrations? | CPO | Low |
| `conversational_coaching` | Not in hierarchy — possibly Team Activity > (Sales Productivity)? | CPO | Low |
| `open_positions_overview` | Not in hierarchy — possibly Team Activity > (Pipeline Creation)? | CPO | Low |
| `order_analysis` | Not in hierarchy — possibly Visit Briefing > (Order Data)? | CPO | Low |
| `customer_prioritisation_*` | Not in hierarchy — possibly Team Activity > (Pipeline Creation)? | CPO | Low |

### Pre-seeded: Missing Figma URLs (from figma_links.md)

| Feature | Gap | Audience | Priority |
|---------|-----|----------|---------|
| Team Activity — Activity Overview | Figma noted as "Poorly documented" — verify content accuracy carefully when writing | CPO | Medium |
| Competitor Analytics | No Figma designs yet — not started | Designer | Medium |
| Visit Report | No Figma URL provided | Designer | Medium |
| Call Log | No Figma URL provided | Designer | Medium |
| Task | No Figma URL provided | Designer | Medium |
| Opportunity | No Figma URL provided | Designer | Medium |
| Lead | No Figma URL provided | Designer | Medium |
| Survey | No Figma URL provided | Designer | Medium |
| Case | No Figma URL provided | Designer | Medium |
| Assistant — Call Functionality | No Figma URL provided | Designer | Medium |
| SAP C4C v2 | No Figma URL provided (C4C v1 auth flow may apply) | Designer | Low |
| Salesforce | No Figma URL provided | Designer | Low |
| MS Dynamics | No Figma URL provided | Designer | Low |
| Aurea | No Figma URL provided | Designer | Low |
| ZOHO | No Figma URL provided | Designer | Low |
| HubSpot | No Figma URL provided | Designer | Low |
| Data Objects (all 9) | No Figma URLs provided | Designer | Low |
| Team Activity — Field Documentation | No Figma URL provided | Designer | Low |

---

### Batch 2 — Playbooks + Visit Analytics

| Feature | Gap | Audience | Priority |
|---------|-----|----------|---------|
| Playbooks — Builder | How many playbooks can be created per workspace/bundle tier? | CPO | Low |
| Playbooks — Builder | Do edits to a published playbook take effect immediately or on next recording? | CPO | Low |
| Playbooks — Builder | Is historical analytics data retained when a playbook is deleted? | Dev | Low |
| Playbooks — Builder | Does a duplicate/copy action exist in the builder UI? | CPO | Low |
| Playbooks — Overview | Can reps see playbook questions before starting a recording (e.g., in visit prep)? | CPO | Low |
| Playbooks — Analytics | Is answer export available? | CPO | Low |
| Visit Analytics — Visit Richness | How often is the richness score updated (per-visit, daily, real-time)? | Dev | Low |
| Visit Analytics — Visit Performance | Navigation route will change — update when new route is confirmed | Dev | Low |
| Playbooks — backend model | Where is the playbook data model in the backend code? (not found in initial scan) | Dev | Medium |

---

### Batch 6 — Assistant

| Feature | Gap | Audience | Priority |
|---------|-----|----------|---------|
| Assistant — App functionality | Offline/sync behavior for interrupted or offline recordings | Dev | Medium |
| Assistant — App functionality | Auto-save / draft behavior if app closed mid-debrief | Dev | Medium |
| Assistant — App functionality | Post-submission edit window for visit reports | CPO | Low |
| Assistant — Call functionality | How are assistant credits purchased/topped up? (process for workspace admin) | CPO | Low |
| Assistant — Call functionality | Exact German phone number to include in docs? | CPO | Low |
| Assistant — Fair Mode | Is Fair Mode tracking ID required or optional when creating a fair? | CPO | Low |

---

## Resolved

| Feature | Gap | Resolution | Date |
|---------|-----|------------|------|
| Visit Analytics — Visit Insight Feed | What does the feed show per visit? | Chronological view of recent visits; separate filtering/search view; helps managers spot interesting visits. | 2026-03-03 |
| Visit Analytics — Visit Performance | Where is it in the UI? | Under Team Activity → Market Intelligence → Visit Performance tab | 2026-03-03 |
| Visit Analytics — Visit Richness | Can reps see their own richness score? | Currently manager-only; rep-facing views planned for future | 2026-03-03 |

---

*Last updated: 2026-03-03*

---

## Batch 1 — Workflows open questions

| # | Page | Question | Audience | Priority |
|---|------|----------|----------|----------|
| 1 | email.md | Can reps add attachments to emails sent via VoiceLine? | Field rep | Medium |
| 2 | email.md | Can reps create named email templates (vs. generic tone guidance)? | Field rep | Low |
| 3 | meeting.md | Can reps create recurring meetings? | Field rep | Low |
| 4 | opportunity.md | For non-complex CRMs (no large product catalog), is opportunity creation always single-step? | Field rep | Medium |
| 5 | visit-report.md | What is the standard "default" visit report schema for new workspaces? (default parts list) | Admin | Low |
| 6 | account.md | Do newly created accounts require admin approval before appearing in the CRM? Is this configurable? | Admin | Medium |
| 7 | contact.md | Is there an explicit "save locally" option for contact records, or is local save automatic? | Field rep | Low |
| 8 | survey.md | Expected launch timeline for Survey workflow? | PM | High |
| 9 | case.md | Expected launch timeline for Case workflow? | PM | High |

---

### Batch 5 — Visit Briefing + CRM Data Quality open questions

| # | Page | Question | Audience | Priority |
|---|------|----------|----------|----------|
| 1 | visit-briefing.md | Is the deduplication similarity threshold configurable per workspace? (what fuzzy match % triggers a duplicate alert?) | Dev | Medium |
| 2 | visit-briefing.md | How far back does VoiceLine data go for activity summary in the briefing? (e.g., last 90 days, all time, configurable?) | CPO | Low |
| 3 | visit-briefing.md | Cross-selling recommendations: expected launch timeline? | PM | High |
| 4 | visit-briefing.md | Order data integration: expected launch timeline? Which ERP/CRM sources? | PM | High |
| 5 | lead-creation.md | When a lead matches an existing contact, does the rep see the contact name + account before confirming the opportunity creation? | CPO | Low |
| 6 | account-creation.md | Are all SAP CRM role types (Prospect, Customer, Partner, etc.) available in all C4C versions? | Dev | Low |
| 7 | account-creation.md | For non-SAP CRMs (Salesforce, Dynamics), are there CRM-specific account type fields? | Dev | Low |
| 8 | customer-data-quality/index.md | Is there a dashboard or report showing how many duplicates were caught by VoiceLine vs. how many made it through? | CPO | Medium |
