---
status: Live
bundles:
  - customer_data
last_updated: 2026-03-06
---

# CRM Data Quality

VoiceLine prevents the most common source of CRM pollution: reps creating duplicate or incorrect records in the field.

## Overview

When a rep creates a new lead, contact, or account in VoiceLine, the system runs an intelligent check before writing anything to the CRM. It searches for existing records that might match, and — if a match is found — it guides the rep to the right action instead of creating a duplicate.

This matters because duplicates in CRM are a persistent, expensive problem. The same company ends up with 3 account records. A known contact gets created as a new lead. Territory reports miscount accounts. Reps fight over assignments to the same customer under different numbers.

VoiceLine's creation flows prevent this at the source — in the field, at the moment the record is captured — rather than through periodic cleanup campaigns.

> [!NOTE]
> Available with the **[Customer Data](../../../commercial/modules.md#customer-data)** module.

## How it works

Each creation flow (lead, contact, account) runs a deduplication check before submission. The rep sees a list of potential matches from the CRM. They can:

- **Select an existing record** to link to instead of creating a duplicate
- **Proceed with creation** if no match applies
- **Trigger follow-up workflows** — some dedup matches unlock smarter actions (for example, a lead that matches an existing account can be converted directly into a contact + opportunity on that account)

## Pages in this section

| Page | What it covers |
|---|---|
| [Lead Creation](./lead-creation.md) | Dedup logic for new leads; lead-to-contact and lead-to-account routing |
| [Contact Creation](./contact-creation.md) | Dedup logic for new contacts; contact-to-account linking |
| [Account Creation](./account-creation.md) | Dedup logic for new accounts; duplicate account handling |

## FAQ

**Is deduplication automatic, or does the rep have to confirm?**
The system surfaces potential matches — the rep always decides. VoiceLine never silently merges or discards records. The goal is to give the rep the right information to make the correct choice, not to override their judgment.

**What if the CRM already has many duplicates?**
VoiceLine prevents new duplicates from being created via the app. It doesn't retroactively clean existing CRM duplicates. Existing data cleanup is a separate CRM administration task.

**Can admins configure the dedup thresholds or matching logic?**
[TBD: not confirmed — check with dev team]
