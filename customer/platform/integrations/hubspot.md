---
status: Live
last_updated: 2026-03-06
---

# HubSpot

Connects VoiceLine to HubSpot via OAuth 2.0, syncing companies, contacts, and deals in both directions.

## Overview

VoiceLine pulls companies, contacts, and deals from HubSpot so reps can search their customer base from the field. When reps submit visit reports, call logs, tasks, or meetings, VoiceLine pushes notes and activity records to the relevant HubSpot company, contact, or deal.

## Where to configure it

Go to **Workspace Settings** → **Integrations** → **HubSpot**.

## Setup

**Prerequisites:**
- HubSpot account with API access (Sales Hub Starter or above)
- Workspace administrator permissions in VoiceLine

**Steps:**
1. Open **Workspace Settings** → **Integrations**
2. Select **HubSpot**
3. Click **Connect with HubSpot** — you'll be redirected to HubSpot's authorization page
4. Log in with your HubSpot administrator account and approve access
5. You're redirected back to VoiceLine — the integration is active and the initial sync begins

## Sync behavior

| Object | Direction | When |
|--------|-----------|------|
| Companies | HubSpot → VoiceLine | On login / scheduled refresh |
| Contacts | HubSpot → VoiceLine | On login / scheduled refresh |
| Deals | HubSpot → VoiceLine | On login / scheduled refresh |
| Visit reports | VoiceLine → HubSpot (Note on company/contact/deal) | On submission |
| Call logs | VoiceLine → HubSpot (Note) | On submission |
| Meetings | VoiceLine → HubSpot (Meeting) | On submission |
| Tasks | VoiceLine → HubSpot (Task) | On submission |
| New contacts | VoiceLine → HubSpot | On submission |
| New companies | VoiceLine → HubSpot (Note) | On submission |
| Deal updates | VoiceLine → HubSpot | On submission |

## Authentication

HubSpot uses **OAuth 2.0**. The workspace administrator completes a one-time browser-based authorization. VoiceLine stores and auto-refreshes the access token.

## FAQ

**Do reps need individual HubSpot accounts?**
No — the workspace-level OAuth connection handles all CRM communication. Reps do not log into HubSpot directly through VoiceLine.

**Which HubSpot object does a visit report sync to?**
Visit report content is pushed as a note linked to the relevant company, contact, or deal depending on the account context of the visit.

**Can VoiceLine update deal stages in HubSpot?**
Yes — when a rep creates or updates an opportunity via voice, VoiceLine can push the updated stage and amount to the linked HubSpot deal.
