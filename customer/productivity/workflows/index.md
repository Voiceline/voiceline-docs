---
status: Live
last_updated: 2026-03-06
---

# Workflows

Create CRM records from the field — by talking, not typing.

## Overview

Workflows are the core output of VoiceLine. After a customer interaction, you open the app, speak, and the structured record appears in your CRM — no manual form filling, no end-of-day documentation backlog.

Each workflow maps to a specific CRM object or action. The assistant extracts the right fields from your voice, pre-fills the form, and lets you review before submitting. Most workflows take under 2 minutes from opening the app to a synced CRM record.

> [!NOTE]
> All workflows below are available with **[Field Sales Fundamentals](../../../commercial/field-sales-fundamentals.md)**. Survey requires the [Marketing Surveys](../../../commercial/modules.md#marketing-surveys) module. Case requires the [Service Cases](../../../commercial/modules.md#service-cases) module.

## Available workflows

| Workflow | What it creates | Status |
|---|---|---|
| [Visit Report](./visit-report.md) | Customer visit record synced to CRM | Live |
| [Call Log](./call-log.md) | Phone call record synced to CRM | Live |
| [Task](./task.md) | Action item for yourself or inside sales | Live |
| [Email](./email.md) | AI-drafted follow-up email, sent directly or via your email client | Live |
| [Reminder](./reminder.md) | Personal calendar reminder in your email client | Live |
| [Meeting](./meeting.md) | Meeting record + calendar invite sent to attendees | Live |
| [Opportunity](./opportunity.md) | New deal or update to existing pipeline entry | Live |
| [Lead](./lead.md) | New prospect by voice or business card scan | Live |
| [Account](./account.md) | New company record with dedup detection | Live |
| [Contact](./contact.md) | New person record by voice or business card scan | Live |
| [Survey](./survey.md) | AI-guided structured data collection | Coming soon |
| [Case](./case.md) | Service case or complaint with queue routing | Coming soon |

## How workflows are triggered

All workflows are accessed from the **+** button in the VoiceLine mobile app. The assistant also detects workflow intent during visit report recordings and may prompt you to create linked records (e.g. an opportunity from a visit where a deal was discussed).

Workflows can also be triggered via the call-in assistant — speak your workflow type and details over the phone.

## Configuring workflows

The fields captured by each workflow are configured by your workspace admin. This means the exact schema of your visit report, lead form, or opportunity record may differ from the defaults described in these docs — it depends on your CRM and workspace setup.

For admin configuration, see [Workflow Customisation](../../platform/workflow-customisation.md).
