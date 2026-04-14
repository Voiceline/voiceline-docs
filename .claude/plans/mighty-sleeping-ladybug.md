# Plan: FSF Implementation Section Rework

## Context

The FSF implementation section (`standard-implementations/`) currently groups content into 3 loosely-named steps (Workspace Configuration, Core Workflows, Reference Data). This doesn't reflect how an SA actually runs an implementation, and mixes technical setup concerns with workflow authoring concerns.

The goal is to restructure the section into 4 clearly scoped phases that mirror the real delivery sequence, enrich each section with content from existing customer docs and product knowledge, and surface new content (recording access, per-object environment pages, pre-populated fields).

---

## Target Structure

### Navigation (docs.json)

Replace the current "Field Sales Fundamentals" nav group with:

```json
{
  "group": "Field Sales Fundamentals",
  "pages": [
    "implementation/standard-implementations/index",
    "implementation/standard-implementations/workspace-setup",
    "implementation/standard-implementations/technical-connection",
    {
      "group": "Phase 3 — Environment Setup",
      "pages": [
        "implementation/standard-implementations/environment-accounts",
        "implementation/standard-implementations/environment-contacts",
        "implementation/standard-implementations/environment-visit-report",
        "implementation/standard-implementations/environment-call-log",
        "implementation/standard-implementations/environment-tasks",
        "implementation/standard-implementations/environment-products",
        "implementation/standard-implementations/environment-competitors",
        "implementation/standard-implementations/environment-industries"
      ]
    },
    {
      "group": "Phase 4 — Workflow Setup",
      "pages": [
        "implementation/standard-implementations/visit-report",
        "implementation/standard-implementations/call-log",
        "implementation/standard-implementations/task",
        "implementation/standard-implementations/email",
        "implementation/standard-implementations/meeting",
        "implementation/standard-implementations/reminder",
        "implementation/standard-implementations/visit-preparation"
      ]
    }
  ]
}
```

Phase 1 (workspace-setup) and Phase 2 (technical-connection) are single pages placed flat before the Phase 3 subgroup.

---

## File Changes

### Files to CREATE

| File | Content source |
|------|---------------|
| `standard-implementations/workspace-setup.mdx` | From `workspace-setup/languages.mdx` + new content |
| `standard-implementations/technical-connection.mdx` | From `workspace-setup/admin-security.mdx` |
| `standard-implementations/environment-accounts.mdx` | From `workspace-setup/crm-data-objects.mdx` (accounts section) |
| `standard-implementations/environment-contacts.mdx` | From `workspace-setup/crm-data-objects.mdx` (contacts section) |
| `standard-implementations/environment-visit-report.mdx` | New — visit record inbound sync from CRM (briefing source) |
| `standard-implementations/environment-call-log.mdx` | New — call record inbound sync from CRM (briefing source) |
| `standard-implementations/environment-tasks.mdx` | From `workspace-setup/crm-data-objects.mdx` (tasks section) |
| `standard-implementations/environment-products.mdx` | From `standard-implementations/product-data.mdx` |
| `standard-implementations/environment-competitors.mdx` | From `standard-implementations/competitor-data.mdx` |
| `standard-implementations/environment-industries.mdx` | New — industry taxonomy setup for analytics |

### Files to UPDATE

| File | Changes |
|------|---------|
| `standard-implementations/index.mdx` | Rewrite overview to describe the 4 phases + what each delivers |
| `standard-implementations/visit-report.mdx` | Add "System-filled fields" section; add component library link |
| `standard-implementations/call-log.mdx` | Add "System-filled fields" section; add component library link |
| `standard-implementations/task.mdx` | Add "System-filled fields" section; add component library link |
| `standard-implementations/email.mdx` | Add "System-filled fields" section; add component library link |
| `standard-implementations/meeting.mdx` | Add "System-filled fields" section; add component library link |
| `standard-implementations/reminder.mdx` | Add "System-filled fields" section; add component library link |
| `standard-implementations/visit-preparation.mdx` | Add component library link |
| `docs.json` | Replace Field Sales Fundamentals nav group as above |

### Files to DELETE

- `standard-implementations/workspace-setup/index.mdx`
- `standard-implementations/workspace-setup/admin-security.mdx`
- `standard-implementations/workspace-setup/languages.mdx`
- `standard-implementations/workspace-setup/crm-data-objects.mdx`
- `standard-implementations/product-data.mdx`
- `standard-implementations/competitor-data.mdx`

---

## Content Detail per New File

### `workspace-setup.mdx` — Phase 1: Setting Up the Workspace

1. **Workspace name** — what it controls (display name, URL slug, sender name in emails), who sets it, when it should be agreed
2. **Language settings** — three distinct concerns:
   - Interface language (what reps see in the app)
   - Recording language (speech recognition model)
   - Output language (AI-generated summaries and reports)
3. **CRM translation** (Enterprise) — reps record in native language, reports generated in rep's language, output translated to workspace language before CRM sync; scoping decision: is this needed?
4. **Custom vocabulary** — products, proper nouns, internal terms added to recognition model; when to collect this
5. **Recording access behavior** — STUB section flagged for expansion; brief description of "who can listen to recordings" feature with access level model; note: full detail pending from user

**Key customer input required:** language matrix per user group, translation requirements, vocabulary list

### `technical-connection.mdx` — Phase 2: Technical Connection

1. **VoiceLine authentication** — Basic (email + password) vs SSO (OAuth 2.0 / SAML); Enterprise only for SSO; what IT needs to provide
2. **CRM connection** — OAuth via service/admin account; required CRM permissions (read + write scope per object); what the SA needs from the CRM admin; step-by-step for each supported CRM
3. **VPN** — when required (on-premise or network-isolated CRM, especially SAP); config options (static IP whitelist vs always-on VPN); MDM-managed VPN notes
4. **MDM app deployment** — App Store + Google Play; MDM enrollment options; what the IT team needs to configure; no custom MDM integration available
5. **Connection validation** — how the SA confirms the connection is live before proceeding to Phase 3

**Key customer input required:** auth method decision, CRM admin credentials, IT/network contact, VPN config if required

### Environment pages — Phase 3

Each page follows the same structure:
1. What data VoiceLine reads from this object (fields synced inbound)
2. Search / metadata configuration (which fields are searchable, phonetic matching, extended fields)
3. Permission and filtering model (how the CRM's existing ownership/territory logic carries over)
4. Sync scope configuration (filters: active only, by territory, by owner, by status)
5. Scoping decisions the SA must resolve before build

**`environment-accounts.mdx`**
- Synced fields: name, customer number, address, city, owner, account type, status
- Search fields: name (default, phonetic), + optional: customer number, city, postal code
- Permission model: CRM owner field OR territory/team-based (SA selects which mirrors the CRM)
- Sync filters: active accounts only, by territory, by account type
- Scoping decisions: which search fields to enable, territory model, active-only filter

**`environment-contacts.mdx`**
- Synced fields: first/last name, email, phone, mobile, job title, department, parent account
- Search: phonetic name matching; results pre-filtered by selected account
- Permission model: inherits from linked account (contact visible = account visible)
- Scoping decisions: account-scoped search vs global contact search, deduplication thresholds (name + account match)

**`environment-visit-report.mdx`** (Visit records from CRM — inbound sync for briefing)
- VoiceLine reads existing CRM visit/activity records to power the Visit Briefing's "recent activity" section
- CRM object mapping per CRM (Activity in Salesforce, Appointment in SAP C4C, etc.)
- History window: default is 12 months
- What's NOT included: records not stored in the account object
- Scoping decisions: activity fields shown in briefing, CRM object type mapping

**`environment-call-log.mdx`** (Call records from CRM — inbound sync for briefing; separate from visit records due to different CRM object types and syncing behavior)
- VoiceLine reads existing CRM call/phone records for the briefing
- CRM object mapping per CRM (Phone Call in SAP C4C, Task with type=Call in Salesforce, etc.)
- History window: default is 12 months
- What's NOT included: records not stored in the account object
- Scoping decisions: call fields surfaced in briefing, direction filter (inbound/outbound)

**`environment-tasks.mdx`**
- Task sync is bidirectional: VoiceLine reads open tasks for briefing; submits new tasks to CRM
- Inbound: open tasks assigned to rep, linked to account/contact
- Outbound: task records created when rep submits a task workflow
- Completion sync: task marked done in CRM → removed from VoiceLine briefing; marked done in VoiceLine → CRM updated
- Scoping decisions: which CRM task types to surface, auto-complete sync toggle

**`environment-products.mdx`** (from product-data.mdx, enriched)
- Why product data is required: without it VoiceLine cannot reliably detect mentions
- Two approaches: (1) real-time API sync (ongoing), (2) one-time JSON upload
- Data must be provided in VoiceLine's JSON format (link to API docs: https://app.getvoiceline.com/api/products/syncing/docs)
- Page explains the concept and decision (sync vs upload), then links out to the API docs for format/implementation
- Scoping decisions: sync method, synonym strategy, who owns ongoing sync maintenance

**`environment-competitors.mdx`** (from competitor-data.mdx, enriched)
- Competitor detection is passive — runs on all recordings automatically
- Required fields: Name; strongly recommended: Aliases (informal names, abbreviations)
- Typical catalogue size: 5–50 competitors
- Detection is prospective only (recordings made after adding a competitor)
- What triggers a "mention": any name or alias match in transcript
- Scoping decisions: initial competitor list, alias strategy, which mentions are analytics-relevant vs noise

**`environment-industries.mdx`** (new)
- Industries are used for segmentation in analytics (Industry Analytics, Visit Analytics filters)
- No standard integration exists — industry setup is custom for every customer
- VoiceLine syncs 1-dimensional industry values only (no hierarchies/trees)
- One account can have multiple industries
- Setup: agree on the industry taxonomy with the customer, configure which CRM field maps to industry, define the list of allowed values
- Scoping decisions: industry list (flat), multi-industry handling, CRM field source

### Phase 4 workflow file updates

Each workflow file gets two additions:

**1. Default schema section**
- Documents the standard set of components the workflow ships with out of the box
- Notes which components can be added, removed, or reconfigured using the component library
- Closes with: _"To add, remove, or change components, see [Component Library](/implementation/workflow-customisation/component-library)."_

**2. Hard-coded fields section**
- Hard-coded fields are SA-configured values that are always submitted to the CRM alongside every workflow submission, regardless of what the rep says or enters
- They do not appear in the UI — the rep never sees or interacts with them
- Example uses: always stamp `Source = VoiceLine`, always set `Activity Type = Field Visit`, always assign to a fixed queue
- The SA defines the field name, the fixed value, and the CRM target field
- Section documents: what hard-coded fields are, when to use them, how to define them, examples per workflow

---

## Execution Order

1. Create new flat files (workspace-setup, technical-connection, environment-*)
2. Update existing workflow files (add system-filled fields + component library link)
3. Update index.mdx
4. Update docs.json
5. Delete old workspace-setup/ subfolder files + product-data.mdx + competitor-data.mdx

---

## Verification

- `mintlify dev` — confirm all nav entries resolve; no broken links
- Check each deleted file path is removed from docs.json
- Confirm the recording access section in workspace-setup.mdx is clearly marked as a stub (not misleading)
- Spot-check cross-links from environment pages to customer docs (e.g. environment-accounts → `/customer/platform/data-objects/accounts`)
