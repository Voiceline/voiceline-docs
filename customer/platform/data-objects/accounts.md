---
status: Live
last_updated: 2026-03-06
---

# Accounts

The primary customer entities in VoiceLine — every field visit is anchored to an account.

## Overview

Accounts represent companies or organizations in your CRM. VoiceLine syncs your full account list so reps can find the right customer while recording a visit report, call log, meeting, or opportunity. The account record is the parent entity for most field activities.

## Where to find it

Accounts are managed in your CRM and sync to VoiceLine automatically. No direct account management UI exists in VoiceLine — to add or modify accounts, update them in the CRM.

Reps access accounts via conversational search during recordings: say or type the account name, and VoiceLine surfaces the matching record.

## Configuration

Accounts sync from your CRM at login and on a scheduled refresh. Fields available in VoiceLine include:

| Field | Description |
|-------|-------------|
| **Name** | Company or organization name |
| **Customer number** | CRM-assigned identifier |
| **Address** | City and address (used for visit location matching) |
| **Owner** | Assigned account owner in the CRM |
| **Account type** | SAP: Prospect, Customer, Prospect & Customer, etc. (CRM-specific) |

Admins can control which accounts are visible to which rep groups via permission settings — see [Search Settings](../search-settings.md).

## Search behavior

Reps find accounts by name during recordings. Phonetic matching is enabled — variations in spelling or pronunciation resolve to the same account. **Favourite accounts** (marked by the rep) appear at the top of results.

Search can also match on customer number or city, depending on your [Search Settings](../search-settings.md) configuration.

## FAQ

**Can reps create new accounts?**
Yes — reps can create new accounts via voice. VoiceLine runs a deduplication check before creation to prevent duplicates. See [Account Creation](../../productivity/customer-data-quality/account-creation.md).

**How often do accounts sync from the CRM?**
Accounts sync on rep login and on a scheduled interval. New accounts created in the CRM become available in VoiceLine at the next sync.

**Does CRM account deletion propagate to VoiceLine?**
Deleted accounts are removed from VoiceLine search at the next sync cycle.
