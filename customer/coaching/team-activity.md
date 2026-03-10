---
status: Live
bundles:
  - field_sales_fundamentals
last_updated: 2026-03-06
---

# Team Activity

See what every rep on your team did today — visits, calls, opportunities, leads — without reading a single report.

## Overview

Team Activity is the manager's operational dashboard. It answers the question: *is my team out there, and what are they doing?* You get a quantitative view of activity across all workflow types, per rep, over any time range you choose.

From the same section, you can drill into an individual rep's profile to see their breakdown in detail, or open field visit reports to read what happened in the field.

> [!NOTE]
> Requires manager-level analytics access. Available with **[Field Sales Fundamentals](../../commercial/field-sales-fundamentals.md)** and **[Sales Coaching Pro](../../commercial/modules.md#sales-coaching-pro)**.

## Where to find it

Web app → **Analytics** → **Team Activity** (`/analytics/activity`).

---

## Activity overview

The main Team Activity view shows the team's combined output over a selected date range.

**Charts:**
- **Distribution pie chart** — share of each workflow type: visit reports, call logs, opportunities, tasks, leads, contacts created. Quickly shows whether the team is primarily documenting visits or generating new pipeline.
- **Daily timeline** — activity volume per day over the selected period. Spot days with unusually low activity or end-of-week spikes.
- **Team member bar chart** — per-rep activity breakdown, filterable by workflow type. Click any rep's bar to open their [Personal Profile](#personal-profiles).

**Filters:**
- Date range (default: last 7 days)
- Team members (filter to specific reps or groups)
- Activity type (drill into one workflow type, e.g. only visit reports)
- Group (for organizations with regional or team-based structures)

**Visit Richness tab (Beta):**
When enabled for your workspace, a second tab shows visit richness data alongside the activity chart. See [Visit Analytics](./visit-analytics.md) for details.

---

## Field documentation

**Field Documentation** gives managers a qualitative view of what the team is actually writing — not just how many visits happened, but what was discussed.

Navigate to **Team Activity → Visit Insights** to see a reverse-chronological feed of recent visit reports from your team. Click any entry to read the full report, including the AI-generated summary, contacts mentioned, and follow-up actions created.

From the feed, you can also open the **"See all visits"** explorer to search and filter across the full visit history.

For analytics layered on top of visit content — visit performance metrics, richness scoring, and the Visit Insight Feed with search — see [Visit Analytics](./visit-analytics.md).

---

## Personal profiles

Click any team member's name or bar in the activity chart to open their **Personal Profile** — a per-rep view of the same data.

The profile shows:

| Metric | What it means |
|---|---|
| Visits | Total visit reports created in the period |
| Actions | All workflow outputs: visits + calls + opportunities + tasks + leads + contacts |
| Sent to CRM | % of created records that were submitted and synced to the CRM |

Below the stat cards:
- **Action type breakdown** — bar chart of how this rep's actions are distributed across workflow types. Useful for spotting a rep who creates many visits but few opportunities, or one who never logs call logs.
- **Activity trend** — daily volume chart for this rep over the selected period.

---

## Coming soon

These analytics views are in development. They will extend Team Activity with deeper commercial insights once available.

### Sales productivity

> [!NOTE]
> **Coming soon.**

Will show visit-to-output conversion metrics — how many visits result in offers, opportunities, or orders — across the team and per rep.

### Pipeline creation

> [!NOTE]
> **Coming soon.**

Will show pipeline generation from field activity — leads, opportunities, and deal volume created from visits — with team-level and rep-level breakdowns.

### Backoffice communication

> [!NOTE]
> **Coming soon.**

Will track task and email handovers from field reps to inside sales — volume, response time, and handover completion rate.

---

## FAQ

**Who can see Team Activity?**
Access is limited to users with analytics permissions (managers and above). Field reps do not see the team view — they see their own [Personal Profile](#personal-profiles) if their workspace grants it.

**Can I filter to a specific region or team?**
Yes. Use the **Group** filter to limit the view to a specific organizational unit. Groups are configured by your workspace admin.

**How often does data update?**
Activity data updates in near real-time as reps submit records from the field.

**Can I export the data?**
[TBD: not confirmed — check with dev team]
