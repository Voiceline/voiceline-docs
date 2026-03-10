---
status: Live
last_updated: 2026-03-06
---

# Search Settings

Control how VoiceLine's conversational search behaves — what records are visible, in what order, and to which reps.

## Overview

VoiceLine's search engine (powered by Typesense) indexes all data objects and makes them conversationally searchable during recordings. Search settings control result scoring, favourites, filtering by ownership, and permission-based visibility — ensuring reps see the right accounts, contacts, and records for their role.

## Where to find it

Search settings are configured by your VoiceLine account manager as part of workspace setup. Contact your account manager to adjust search behavior.

> [!NOTE]
> **Favourites** are set by individual reps directly in the app — no admin action required.

## Search behavior

When a rep speaks or types a search term, VoiceLine:

1. Runs a **phonetic match** — handles name variations, spelling differences, and pronunciation alternatives
2. Applies **ownership / permission filters** — returns only records the rep is authorized to see
3. Scores results by **relevance + recency** — frequently visited or recently interacted-with records rank higher
4. Surfaces **favourites** at the top of results

Standard search looks up records by name. **Extended search** (where enabled) also searches across additional fields: customer number, city, email, phone, and owner name.

## Favourites

Reps can mark any account, contact, or other record as a favourite. Favourited records appear at the top of search results for that rep.

To favourite a record: find the record in search results → tap the star icon. Favourites are per-rep and do not affect other users' search results.

## Ownership and permission filters

By default, search returns all records in the workspace. Two modes restrict visibility:

| Mode | Behavior |
|------|---------|
| **CRM user permissions** | Each rep sees only accounts/contacts assigned to them in the CRM (by owner field) |
| **Team filter** | Each rep sees only records belonging to their CRM team or group |

These modes are configured per workspace by your account manager. They are typically used when reps operate in clearly defined territories and should not see each other's accounts.

## Extended search fields

When **extended search** is enabled, reps can find accounts by:
- Customer number
- City / address
- Email address
- Owner name

This is useful for large account lists where searching by name alone is ambiguous.

## FAQ

**Why doesn't a rep see a record they expect to find?**
Check ownership filters — if CRM user permissions are enabled, the record may be assigned to a different owner in the CRM. Verify the CRM owner field on the record.

**Can reps search records outside their assigned territory?**
Only if CRM user permissions or team filter are not enabled. With those modes on, reps see only their assigned records.

**How often are search results updated?**
The search index updates in near-real-time as records sync from the CRM. New records are searchable within minutes of the CRM sync completing.

**Can admins see all records regardless of permission filters?**
Permission filters apply to all users including admins in the rep-facing search. Admin analytics views are not subject to the same restrictions.
