---
status: Live
bundles:
  - customer_data
last_updated: 2026-03-06
---

# Lead Creation

VoiceLine checks three layers of your CRM before creating a new lead — and routes you to the right action based on what it finds.

## Overview

Creating a lead sounds simple, but the field reality is messier: the "new" prospect you just met might already be in your CRM as a contact at an existing account. Or someone already created a lead for them last quarter. Creating a duplicate doesn't just add noise — it fragments the customer history, splits follow-up ownership, and eventually breaks territory reports.

VoiceLine's lead creation flow runs a cascade of checks before writing anything to your CRM. The rep sees what already exists and decides how to proceed.

> [!NOTE]
> Available with the **[Customer Data](../../../commercial/modules.md#customer-data)** module.

## Deduplication cascade

When you create a lead — by voice or by business card scan — VoiceLine checks the CRM in this order:

### 1. Existing lead check
Does a lead already exist with this name or company?

If yes: you see the existing lead record. You can open it to review the status, update it with new context from your conversation, or confirm it's a different person and proceed with creation.

### 2. Existing contact check
Does a contact already exist for this person at an existing account?

If yes: this person is already a known contact in your CRM. Creating a new lead would be the wrong object type. Instead, VoiceLine guides you to:
- Link your recording to the existing contact
- Create a new **opportunity** on the associated account if there's buying interest

### 3. Existing account check
Does the company already exist as an account, even if this specific person isn't a contact yet?

If yes: you don't need a new lead — you need a new **contact** on that account. VoiceLine guides you to:
- Create a **contact** linked to the existing account
- Optionally create an **opportunity** on the account at the same time

### No match found
If none of the checks find a match, lead creation proceeds normally. The new lead is written to your CRM.

## What syncs to your CRM

When a lead is created (no dedup match):

| Field | Content |
|---|---|
| Name, title, company | From voice or business card |
| Phone, email | From voice or business card |
| Lead source | Configurable (Trade Fair, Cold Outbound, etc.) |
| Notes | From your voice recording |

When routed to contact + opportunity (dedup match on account):
- A new contact is created on the existing account
- An opportunity record is created if buying intent was mentioned
- The original lead record is not created

## FAQ

**What if the matching CRM record is wrong (different person, same name)?**
You can always skip all suggestions and proceed with creating a new lead. The dedup flow presents options — it doesn't block creation.

**Does the cascade run in real time during the recording?**
No. The check runs after you finish recording and tap to review your draft. The results appear in the review screen before you submit.

**Is business card scanning covered by the same dedup logic?**
Yes. Both voice creation and business card scanning run the same deduplication cascade.
