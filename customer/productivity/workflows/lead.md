---
status: Live
bundles:
  - customer_data
last_updated: 2026-03-06
---

# Lead

Capture a new prospect from the field in under a minute — by voice or business card.

## Overview

A lead in VoiceLine is a new potential customer that doesn't yet exist in your CRM. You create a lead when you meet someone new — at a trade fair, during a cold outbound visit, or from a referral.

Two capture methods:

- **Voice** — describe the lead by speaking; the AI extracts contact and company details
- **Business card scan** — photograph the card; the AI reads the text and populates the lead fields

Both methods check your CRM for duplicates before creating the record.

> [!NOTE]
> Available with the **[Customer Data](../../../commercial/modules.md#customer-data)** module.

## Where to find it

Open the VoiceLine mobile app → tap **+** → select **Lead**.

For business card scanning, you can also tap the camera icon directly from the home screen — see [Business Card Scanner](../assistant.md#adding-context).

## Creating a lead

### By voice

1. **Open Lead** from the + menu.
2. **Speak the details** — name, company, role, phone, email, and any context about their interest. Example: *"New lead: Marco Brunetti, Purchasing Manager at Acero SpA in Milan, interested in our fastener range, got his contact from the Hannover Messe."*
3. **Review the draft** — the AI populates all available fields.
4. **Handle deduplication** — if VoiceLine finds a potential match in your CRM, it shows you the existing record. You can link to it, create a new one, or cancel.
5. **Submit** — the lead is created in your CRM.

### By business card

1. **Photograph the card** — front and back. The AI reads all text on the card.
2. **Review the extracted data** — name, title, company, phone, email, address.
3. **Handle deduplication** — same as above.
4. **Add a recording** (optional) — speak context about this lead before submitting.
5. **Submit**.

## Deduplication

Before creating a lead, VoiceLine searches your CRM for potential duplicates based on name and company. If matches are found:

- You see a list of possible duplicates with their details
- You can select an existing record to link to (instead of creating a duplicate)
- Some deduplication flows trigger follow-up actions — for example, matching a lead to an existing account may prompt you to create an opportunity on that account

## What syncs to your CRM

| Field | Content |
|---|---|
| Name, title, company | Extracted from voice or business card |
| Phone, email | Extracted from voice or business card |
| Lead source | Configurable (e.g. Trade Fair, Cold Outbound) |
| Notes / interest context | From your voice recording |
| Owner | Assigned to creating rep |

## FAQ

**What if the lead turns out to be an existing customer?**
The deduplication flow will surface this. You can link to the existing account and create an opportunity, rather than creating a duplicate lead.

**Can I create a lead during a trade fair?**
Yes — business card scanning is optimized for high-volume trade fair scenarios. See [Industry Fair Mode](../assistant.md#fair-mode) for the full fair workflow.

**Does the business card scanner work for any language?**
The AI reads text in all major languages. Card text quality (print, photos, glossy finish) affects extraction accuracy.

**What happens after a lead is created?**
The lead appears in your CRM for follow-up. Depending on your sales process, it may be qualified and converted to a contact + account + opportunity.
