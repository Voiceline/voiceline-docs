---
status: Live
last_updated: 2026-03-06
---

# SAP Cloud for Customer (v1)

Connects VoiceLine to SAP C4C using the OData API (v1), enabling two-way sync of accounts, contacts, leads, and field activities.

## Overview

VoiceLine pulls accounts, contacts, leads, and opportunities from SAP C4C so reps can search their customer base during visits. When a rep submits a visit report or creates an action, VoiceLine pushes the record back to SAP as a structured appointment, phone call, or task on the relevant account or contact.

## Where to configure it

Go to **Workspace Settings** → **Integrations** → **SAP Cloud for Customer (v1)**.

## Setup

**Prerequisites:**
- SAP C4C tenant URL
- Service user credentials (username + password) with OData API access
- Network access to your SAP tenant (VPN may be required — see [Integrations](./index.md#network-requirements))

**Steps:**
1. Open **Workspace Settings** → **Integrations**
2. Select **SAP Cloud for Customer (v1)**
3. Enter your SAP tenant URL, username, and password
4. Click **Test connection** — VoiceLine verifies the credentials and confirms API access
5. Save — VoiceLine begins the initial sync

## Sync behavior

| Object | Direction | When |
|--------|-----------|------|
| Accounts | SAP → VoiceLine | On login / scheduled refresh |
| Contacts | SAP → VoiceLine | On login / scheduled refresh |
| Leads | SAP → VoiceLine | On login / scheduled refresh |
| Opportunities | SAP → VoiceLine | On login / scheduled refresh |
| CRM users (employees) | SAP → VoiceLine | On login |
| Visit reports | VoiceLine → SAP (Appointment) | On submission |
| Call logs | VoiceLine → SAP (Phone Call) | On submission |
| Tasks | VoiceLine → SAP (Task) | On submission |

## Authentication

SAP C4C v1 uses **Basic authentication** — service user credentials are stored in VoiceLine's integration settings and are used for all API calls. Credentials are encrypted at rest.

> [!NOTE]
> VoiceLine requires a dedicated service user account in SAP C4C, not an individual rep's login credentials. The service user must have OData API permissions for the objects listed above.

## FAQ

**Can I use SSO for the SAP integration?**
No — SAP C4C v1 uses Basic auth (service user). Individual reps authenticate to VoiceLine separately using their own credentials.

**What is the difference between SAP C4C v1 and v2?**
v1 uses the older OData API and supports a broader range of SAP C4C deployments. v2 uses a newer API surface with different object types and push behaviors. Your SAP configuration determines which version to use — check with your SAP administrator.

**How often does data sync from SAP to VoiceLine?**
Account and contact data syncs on rep login and on a scheduled interval. Records created in SAP after the last sync become available in VoiceLine at the next refresh.
