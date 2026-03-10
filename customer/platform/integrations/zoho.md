---
status: Live
last_updated: 2026-03-06
---

# ZOHO CRM

Connects VoiceLine to ZOHO CRM via OAuth 2.0, syncing accounts, contacts, and deals in both directions.

## Overview

VoiceLine pulls accounts, contacts, and deals from ZOHO CRM so reps can search their customer base from the field. When reps submit visit reports, call logs, or tasks, VoiceLine pushes these as structured activity records linked to the relevant account, contact, or deal in ZOHO.

## Where to configure it

Go to **Workspace Settings** → **Integrations** → **ZOHO CRM**.

## Setup

**Prerequisites:**
- ZOHO CRM account with API access
- Workspace administrator permissions in VoiceLine

**Steps:**
1. Open **Workspace Settings** → **Integrations**
2. Select **ZOHO CRM**
3. Click **Connect with ZOHO** — you'll be redirected to ZOHO's authorization page
4. Log in with your ZOHO administrator account and grant access
5. You're redirected back to VoiceLine — the integration is active

## Sync behavior

| Object | Direction | When |
|--------|-----------|------|
| Accounts | ZOHO → VoiceLine | On login / scheduled refresh |
| Contacts | ZOHO → VoiceLine | On login / scheduled refresh |
| Deals | ZOHO → VoiceLine | On login / scheduled refresh |
| Visit reports | VoiceLine → ZOHO (Appointment) | On submission |
| Call logs | VoiceLine → ZOHO (Call Log) | On submission |
| Tasks | VoiceLine → ZOHO (Task) | On submission |
| Notes on accounts/contacts | VoiceLine → ZOHO | On submission |

## Authentication

ZOHO CRM uses **OAuth 2.0**. The workspace administrator completes a one-time authorization via ZOHO's login page. VoiceLine stores and auto-refreshes the access token.

## FAQ

**Which ZOHO CRM editions are supported?**
VoiceLine requires ZOHO CRM API access, available from ZOHO CRM Standard edition and above.

**Can I push deals to ZOHO?**
Yes — deals synced from ZOHO are searchable in VoiceLine. Reps can create and update opportunities via voice, which sync back to ZOHO as deal updates.
