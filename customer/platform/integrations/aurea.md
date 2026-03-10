---
status: Live
last_updated: 2026-03-06
---

# Aurea CRM

Connects VoiceLine to Aurea CRM using Basic authentication, enabling account data sync and outbound field activity logging.

## Overview

VoiceLine pulls account activity history from Aurea CRM so reps have context before and during visits. When reps submit field activities, VoiceLine pushes appointments, call logs, tasks, leads, and project records back to Aurea on the relevant account.

## Where to configure it

Go to **Workspace Settings** → **Integrations** → **Aurea CRM**.

## Setup

**Prerequisites:**
- Aurea CRM instance with API access
- Service user credentials (username + password)
- Network access to your Aurea instance (VPN may be required — see [Integrations](./index.md#network-requirements))

**Steps:**
1. Open **Workspace Settings** → **Integrations**
2. Select **Aurea CRM**
3. Enter your Aurea instance URL and service user credentials
4. Click **Test connection**
5. Save — VoiceLine begins syncing account data

## Sync behavior

| Object | Direction | When |
|--------|-----------|------|
| Account activity history | Aurea → VoiceLine | On account open |
| Visit reports | VoiceLine → Aurea (Appointment) | On submission |
| Call logs | VoiceLine → Aurea (Call) | On submission |
| Tasks | VoiceLine → Aurea (Task) | On submission |
| New leads | VoiceLine → Aurea | On submission |
| Projects | VoiceLine → Aurea | On submission |

## Authentication

Aurea CRM uses **Basic authentication** — service user credentials are stored in VoiceLine's integration settings, encrypted at rest.

## FAQ

**Does VoiceLine pull full account records from Aurea?**
VoiceLine primarily pulls activity history from Aurea accounts. Full account record sync (name, address, contact persons) may require additional configuration depending on your Aurea deployment.

**Is the VPN requirement specific to Aurea?**
Corporate Aurea deployments are often hosted on-premise or in private networks. Check with your IT team to ensure VoiceLine's servers can reach your Aurea API endpoint.
