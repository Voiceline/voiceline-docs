---
status: Live
last_updated: 2026-03-06
---

# Data Objects

The master records that VoiceLine makes searchable and referenceable for reps in the field.

## Overview

Data objects are the entities reps interact with during visit recordings — accounts, contacts, leads, products, competitors, and more. Most objects are synced from your CRM; some are managed directly in VoiceLine. All objects are indexed in VoiceLine's conversational search engine so reps can find them by name during recordings.

## Where to manage them

Go to **Workspace Settings** to configure individual data objects:

| Object | Configuration location |
|--------|----------------------|
| [Competitors](./competitors.md) | Workspace Settings → Competitors |
| [Products](./products.md) | Workspace Settings → Product Recognition |
| All others | Configured via [Integrations](../integrations/index.md) — synced from CRM |

## Available data objects

| Object | Source | Used in |
|--------|--------|---------|
| [Accounts](./accounts.md) | CRM | All field activities |
| [Contacts](./contacts.md) | CRM + rep-created | Call logs, meetings, leads |
| [Leads](./leads.md) | CRM + rep-created | Lead creation, dedup |
| [Opportunities](./opportunities.md) | CRM + rep-created | Opportunity creation / update |
| [Products](./products.md) | CRM / manual upload | Opportunity creation, cross-selling |
| [Competitors](./competitors.md) | Manually managed | Competitive intelligence extraction |
| [Meetings](./meetings.md) | VoiceLine → CRM | Meeting creation workflow |
| [Tasks](./tasks.md) | VoiceLine → CRM | Task creation workflow |
| [Industries](./industries.md) | CRM / manual | Market analytics segmentation |

## Search behavior

All data objects are searched conversationally — reps speak or type a name and VoiceLine returns matching records. Search is phonetic: "Müller" and "Mueller" resolve to the same result. Favourite records are surfaced first.

See [Search Settings](../search-settings.md) for visibility, scoring, and permission configuration.

## FAQ

**Who can add or edit data objects?**
Workspace administrators manage competitor lists and product catalogs directly. All other objects sync automatically from your CRM — edits should be made in the CRM and will sync to VoiceLine at the next refresh.

**What happens if a record exists in VoiceLine but not in the CRM?**
Records created by reps (new accounts, contacts, leads) are pushed to the CRM on submission. Once in the CRM, they sync back like any other record.
