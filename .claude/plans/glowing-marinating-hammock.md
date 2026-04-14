# Plan: Rework the Implementation Tab

## Context

The Implementation tab was written with the right technical content but the wrong posture. It reads like a constraint document — a list of what customers can't do, what's not included, and what requires extra scoping. The result: a customer reading it feels like they're about to enter a painful IT project rather than engage with an expert partner who has implemented this hundreds of times.

The goals of this rework:
- Shift tone from restrictive/technical → expert-led and collaborative
- Make the customer journey immediately obvious (what happens, when, in what order)
- Restructure the FSF setup section so it reads as a guided walkthrough, not a scattered reference
- Remove all process-specific language ("scoping session") — write to the data and decisions, not the meetings
- Every page should make the customer feel: "I'm in the best hands. This is going to go well."

---

## Proposed New Structure

### Current nav vs proposed nav

| Current | Proposed |
|---------|----------|
| Getting Started → Overview | **Overview** (new: partnership framing, not philosophy doc) |
| Getting Started → Phase 1 FSF | **Your implementation journey** (new: visual timeline, phases as milestones) |
| Getting Started → Phase 2 Expansion | ↑ merged into above |
| Getting Started → Example Timelines | ↑ merged into above |
| Field Sales Fundamentals → Standard Implementations | **Setting up Field Sales Fundamentals** (renamed + restructured as a step-by-step guide) |
| Standard Implementations → [flat list of 10 workflows] | ↑ grouped into setup steps (see below) |
| Workflow Customisation | **Customisation** (unchanged structure, tone fix only) |
| Modules | **Modules** (unchanged structure, minor tone fix) |
| Data & Integrations | unchanged |
| Security & Compliance | unchanged |

---

## Phase-by-phase change plan

### 1. `implementation/index.mdx` — Full rewrite

**Problem:** Currently reads as a philosophy doc with lists of "what this section covers." Dry and abstract.

**Fix:** Rewrite as the "Welcome to your implementation" page. Convey:
- VoiceLine is a managed implementation — you don't run an internal IT project
- Your Solutions Architect guides you from first call to go-live
- The platform is built on field sales best practices from 100s of leading organisations
- There's a proven sequence; here's the overview
- Then link to the journey page

Tone model: confident, warm, expert — like a senior consultant briefing a new client.

---

### 2. `implementation/our-approach/` — Consolidate into one "journey" page

**Problem:** Three separate pages (Phase 1 FSF, Phase 2 Expansion, Example Timelines) fragment a story that belongs together. Phase 1 reads as a rules doc ("no other modules activated," "90-day window"). The example timelines page is useful but buried.

**Fix:** Replace the three pages with **two pages**:
- `our-approach/how-we-work.mdx` (new) — the full journey told as a narrative:
  - What the customer brings; what VoiceLine brings
  - Phase 1: FSF setup (4–6 weeks) — explained as building the foundation, not as a restriction
  - Phase 2: Steady state & adoption (weeks 6–12) — described as the "proving ground"
  - Phase 3: Expand with modules — described as "unlocking more capability"
  - Inline example timelines table at the bottom (not a separate page)
  - Key framing: "why this sequence works" — not rules, but reasoning from experience

- Keep `our-approach/phase-2-expansion.mdx` but rename to `our-approach/expanding-with-modules.mdx` with a brief rewrite — just covers the module expansion cycle

Delete `our-approach/example-timelines.mdx` (merged into above).

---

### 3. `implementation/standard-implementations/` — Restructure as a guided walkthrough

**Problem:** The current structure is a flat list of 10 workflows (visit report, call log, task, email, meeting, reminder, visit prep, product data, competitor data) plus 4 workspace setup pages. There's no logical sequence. Customers don't know where to start or what order things happen in.

**Fix:** Restructure into **numbered setup steps**. The heading of each group signals where we are in the process:

**New grouping:**
```
standard-implementations/
  index.mdx                    ← intro: "Here's how we set up FSF — in this order"
  
  step-1-workspace/            ← rename from workspace-setup/
    index.mdx                  ← "Before workflows, we configure your workspace"
    admin-security.mdx         ← unchanged content, tone fix
    languages.mdx              ← unchanged content, tone fix
    crm-data-objects.mdx       ← unchanged content, tone fix
  
  step-2-core-workflows/       ← new grouping: the 6 daily workflows
    index.mdx                  ← "These are the workflows your reps will use every day"
    visit-report.mdx
    call-log.mdx
    task.mdx
    email.mdx
    meeting.mdx
    reminder.mdx
  
  step-3-reference-data/       ← new grouping: products + competitors
    index.mdx                  ← "Load your reference data so AI recognition is accurate from day one"
    product-data.mdx
    competitor-data.mdx
```

The `index.mdx` for the whole section becomes a short guided intro:
> "Setting up FSF takes [X days of SA time]. Here's what we do, in order. You'll be involved at each step — mostly to make decisions about your sales process. We handle the configuration."

Each step's index page explains: what this step covers, who does it, what decisions the customer needs to make.

**Key tone change across all workflow pages:**
- Remove or reframe all "Not included" sections — currently these read as a wall of limitations. Replace with a single `<Note>` at the bottom: "Need something beyond this standard? [Talk to your SA](/implementation/workflow-customisation/additional-customisation)" 
- Reframe "Configurable" sections as "How we tailor this for you" — same content, different posture
- Remove all mentions of "scoping session" — replace with "during setup" or "your SA will confirm these with you"

---

### 4. `implementation/standard-implementations/index.mdx` — New intro page

Currently just a brief overview. Needs to become the orientation page for the FSF setup section — tells the customer:
1. This section is for your SA, not for self-service configuration
2. Here's the sequence (Step 1 → 2 → 3)
3. What you need to bring to each step (decisions, not technical work)
4. What you'll have when it's done

---

### 5. `implementation/workflow-customisation/additional-customisation.mdx` — Tone fix

**Problem:** This page explains what VoiceLine won't build and why. It's necessary content but currently reads combatively.

**Fix:** Reframe as "How we grow the platform together":
- Lead with: most customers get everything they need from the standard platform + component library
- The evaluation criteria become: "how we decide what's worth building for everyone" — not a rejection framework
- The fee becomes: "non-standard CRM integrations require dedicated engineering time" — not a gatekeeping line
- Soften without removing the substance

---

### 6. `implementation/our-approach/phase-1-fsf.mdx` — Delete

Merge into new `how-we-work.mdx`. The 90-day rule and rationale stays — but told as "here's why this sequence works" rather than "here are the rules."

---

## Tone guidelines for all rewrites

**Replace restriction language:**
| Current phrasing | New phrasing |
|-----------------|--------------|
| "Not included" | *(move to a single Note callout)* |
| "No other modules activated during Phase 1" | "FSF runs solo for the first 90 days — this is intentional. It's the fastest path to adoption." |
| "Scoping session" | "your SA will confirm with you" / "during setup" |
| "Standard implementations are CRM-agnostic by design" | "The standard works across all CRMs — your SA handles the CRM-specific mapping" |
| "Custom code outside standard model" | *(just omit)* |
| "Bespoke workflows" → won't build | *(reframe)* "If your process doesn't fit — that's our cue to consult on simplification first" |

**Replace passive/abstract with active/concrete:**
- "Implementation happens in phases" → "Here's exactly what we do, and when"
- "Customisation is available" → "Your SA will tailor each workflow to your process"

---

## Files to create/modify

| File | Action |
|------|--------|
| `implementation/index.mdx` | Full rewrite |
| `implementation/our-approach/phase-1-fsf.mdx` | Delete — content merged |
| `implementation/our-approach/phase-2-expansion.mdx` | Rewrite as `expanding-with-modules.mdx` |
| `implementation/our-approach/example-timelines.mdx` | Delete — content merged |
| `implementation/our-approach/how-we-work.mdx` | **New file** — the unified journey page |
| `implementation/standard-implementations/index.mdx` | Full rewrite |
| `implementation/standard-implementations/workspace-setup/` → `step-1-workspace/` | Rename dir + update index, tone-fix sub-pages |
| `implementation/standard-implementations/step-2-core-workflows/` | **New grouping dir** — move 6 workflow files + new index |
| `implementation/standard-implementations/step-3-reference-data/` | **New grouping dir** — move product + competitor files + new index |
| `implementation/workflow-customisation/additional-customisation.mdx` | Tone rewrite |
| `docs.json` | Update nav to reflect new structure |

---

## What is NOT changing

- All technical content (field names, CRM objects, component specs, sync behaviour) — stays as-is
- Module implementation pages — structure unchanged, minor tone polish only
- Data & Integrations page
- Security & Compliance page
- Component library (too large to rewrite; tone is already more neutral/reference)

---

## Verification

1. Read the new `index.mdx` and `how-we-work.mdx` cold — does a prospect immediately understand what the implementation looks like?
2. Walk through the FSF setup section — does Step 1 → 2 → 3 feel like a guided walkthrough?
3. Ctrl+F "not included" across all rewrites — should return 0 results (replaced with Note callouts)
4. Ctrl+F "scoping session" — should return 0 results
5. Check `docs.json` renders correct navigation in Mintlify preview
