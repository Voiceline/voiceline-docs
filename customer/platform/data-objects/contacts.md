---
status: Live
last_updated: 2026-03-06
---

# Contacts

People at accounts — referenced in call logs, meetings, leads, and outreach actions.

## Overview

Contacts represent individual people at your customer accounts. VoiceLine syncs contacts from your CRM so reps can link field activities to the right person. Reps can also create new contacts via voice or business card scan when they meet someone new.

## Where to find it

Contacts sync from your CRM automatically. Reps access contacts via conversational search when creating a call log, meeting, or lead: say the contact's name, and VoiceLine matches the record.

## Configuration

| Field | Description |
|-------|-------------|
| **Name** | First + last name |
| **Email** | Primary email address |
| **Phone** | Phone number |
| **Account** | Parent account (company) |
| **Owner** | CRM-assigned owner |

## Search behavior

Contacts are searched by name during recordings. Phonetic matching handles name variations. Results show the contact's account name for disambiguation when multiple contacts share a name.

Contacts are filtered by the account selected earlier in the recording flow — VoiceLine surfaces contacts linked to that account first.

## FAQ

**Can reps create contacts in the field?**
Yes — via voice or business card scan. VoiceLine checks for duplicates before creating. See [Contact Creation](../../productivity/customer-data-quality/contact-creation.md).

**What happens to a contact created in VoiceLine before a CRM account exists?**
Contacts require a linked account. If no matching account is found during creation, VoiceLine may prompt the rep to create an account first, or save the contact locally until the account is confirmed.

**Are contacts visible to all reps or only to the owner?**
Visibility is controlled by [Search Settings](../search-settings.md) permission configuration.
