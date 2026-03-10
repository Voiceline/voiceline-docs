---
status: Live
last_updated: 2026-03-06
---

# Meetings

Follow-up appointments created by reps after field visits — synced to both the CRM and attendee calendars.

## Overview

Meetings in VoiceLine represent scheduled follow-up appointments created during or after a visit. When a rep creates a meeting via voice, VoiceLine pushes a CRM appointment record and sends calendar invites to all attendees — without the rep opening a calendar app or CRM.

## Where to find it

Meetings are created via the VoiceLine assistant — they are not a browse/search object. After submission, meetings appear in your CRM as appointment or event records on the relevant account.

## Configuration

Meeting records contain the following fields:

| Field | Description |
|-------|-------------|
| **Subject** | Meeting title or purpose |
| **Date / time** | Scheduled date and time range |
| **Attendees** | Reps and customer contacts invited |
| **Account** | Linked CRM account |
| **Notes** | Agenda or context for the meeting |

Attendees receive calendar invites directly — no manual calendar management required.

## CRM sync

| Object | Direction | CRM record type |
|--------|-----------|----------------|
| Meeting | VoiceLine → CRM | Appointment (SAP) / Event (Salesforce) / Appointment (Dynamics) |
| Calendar invite | VoiceLine → Attendee email | Calendar event |

## FAQ

**How is a Meeting different from a Reminder?**
A [Reminder](../../productivity/workflows/reminder.md) creates a personal calendar entry in the rep's email client — no CRM record, no attendees. A Meeting creates a CRM appointment and sends invites to all listed attendees.

**Can reps create recurring meetings?**
Not currently — each meeting is a single scheduled appointment.

**What happens if an attendee's email isn't in VoiceLine?**
The attendee must be a CRM contact with a valid email address for the calendar invite to be sent.
