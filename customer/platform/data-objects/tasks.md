---
status: Live
last_updated: 2026-03-06
---

# Tasks

Follow-up actions assigned to reps or inside sales — synced to the CRM as task records.

## Overview

Tasks in VoiceLine represent structured follow-up actions created during field recordings. When a rep identifies something that needs to happen after a visit — a callback, a sample send, an internal handover — they create a task via voice. VoiceLine pushes the task to the CRM and optionally notifies the assigned person.

## Where to find it

Tasks are created via the VoiceLine assistant during or after a visit. After submission, tasks appear in your CRM as task records on the relevant account or contact.

## Configuration

| Field | Description |
|-------|-------------|
| **Title** | Task description |
| **Due date** | When the task should be completed |
| **Assigned to** | Rep or inside sales colleague responsible |
| **Account** | Linked CRM account |
| **Notes** | Additional context |

Tasks can be assigned to the recording rep or to another team member (e.g., an inside sales colleague for follow-up email or quote preparation).

## CRM sync

| Object | Direction | CRM record type |
|--------|-----------|----------------|
| Task | VoiceLine → CRM | Task (all supported CRMs) |

## FAQ

**How is a Task different from a Reminder?**
A [Reminder](../../productivity/workflows/reminder.md) creates a personal calendar entry for the rep only — no CRM record, not assignable to others. A Task syncs to the CRM and can be assigned to any team member.

**Can tasks be assigned to someone outside the VoiceLine workspace?**
Tasks are assigned to CRM users. The assignee must exist as a user in your CRM — they receive the task there, not through VoiceLine directly.

**Are tasks visible in VoiceLine after creation?**
Tasks are managed in the CRM after creation. VoiceLine is the capture tool — ongoing task management happens in your CRM.
