---
status: Live
last_updated: 2026-03-06
---

# Integrations

Connect VoiceLine to your CRM so field data flows directly into your system of record — without reps touching the CRM manually.

## Overview

VoiceLine integrates with your CRM in two directions. Inbound: accounts, contacts, and other records sync from your CRM into VoiceLine so reps can search and reference them during visits. Outbound: visit reports, call logs, tasks, opportunities, and other actions created by reps sync back to the CRM automatically.

All integration configuration is handled by a workspace administrator. Reps do not need to configure anything.

## Where to configure it

Go to **Workspace Settings** → **Integrations**.

## Supported CRMs

| CRM | Auth method | Status |
|-----|-------------|--------|
| [SAP Cloud for Customer (v1)](./sap-c4c-v1.md) | Basic (username + password) | Live |
| [SAP Cloud for Customer (v2)](./sap-c4c-v2.md) | Basic (username + password) | Live |
| [Salesforce](./salesforce.md) | OAuth 2.0 | Live |
| [Microsoft Dynamics 365](./ms-dynamics.md) | OAuth 2.0 | Live |
| [Aurea CRM](./aurea.md) | Basic (username + password) | Live |
| [ZOHO CRM](./zoho.md) | OAuth 2.0 | Live |
| [HubSpot](./hubspot.md) | OAuth 2.0 | Live |

## Network requirements

Some CRM environments (particularly SAP deployments) are accessible only via corporate VPN or a whitelisted IP range. Ensure VoiceLine's servers are reachable from within your CRM's network perimeter before starting setup. Contact your IT team to confirm firewall rules if the connection test fails during setup.

## FAQ

**Can VoiceLine connect to a CRM not listed here?**
Contact your VoiceLine account manager. Additional integrations are evaluated based on customer demand.

**Who manages the integration credentials?**
A workspace administrator stores CRM credentials in VoiceLine's integration settings. Credentials are encrypted at rest. Individual reps do not need CRM login access to use VoiceLine.

**What happens if the CRM connection drops?**
VoiceLine queues outbound records and retries delivery. Reps are not blocked from creating records — they sync once the connection is restored.
