Review and merge all open documentation PRs in voiceline-docs (https://github.com/Voiceline/voiceline-docs). These PRs are typically proposed by the Mintlify agent, which scans the backend, frontend, and mobile repositories for merged changes and proposes corresponding doc updates. Human contributors may also open PRs.

Follow the phases below in order. **Never advance past a gate without explicit user confirmation.**

---

## Phase 1 — Save local state and sync to main

1. Record the current branch: `git branch --show-current`
2. Check for local changes: `git status --short`
3. If there are any uncommitted changes or untracked `.mdx`/`.md` files:
   - Stash everything including untracked files:
     `git stash push --include-untracked -m "pre-review-prs-$(date +%Y%m%d-%H%M%S)"`
   - Record the stash name so it can be restored in Phase 5
4. Switch to main and pull latest: `git checkout main && git pull`

---

## Phase 2 — Collect and analyse all open PRs

Run: `gh pr list --state open --limit 50 --json number,title,headRefName,author,body,url`

For each PR:
- Get the list of changed files: `gh pr diff {number} --name-only`
- Extract affected page paths from the PR body (look for Mintlify paths like `/customer/...`, `/implementation/...`, bold filenames, or any `.mdx`/`.md` references)

Build a conflict map:
- **Inter-PR conflicts**: any `.mdx` or `.md` file that appears in 2 or more PRs — flag both PRs and the shared file path
- **Git conflicts with main**: for each PR branch run:
  `git fetch origin {headRefName} 2>/dev/null && git merge-tree $(git merge-base origin/{headRefName} main) main origin/{headRefName}`
  If the output contains `<<<<<<<` conflict markers, flag this PR as having a git conflict with main

---

## Phase 3 — Present overview

Present a clean summary in this exact format:

### Open PRs ({n} total)

| # | Title | Author | Affected pages | Status |
|---|-------|--------|----------------|--------|
| #8 | Document workflow picker | mintlify[bot] | `/customer/productivity/workflows`, `/customer/platform/workflow-customisation` | ✓ Clean |
| #6 | ... | ... | ... | ⚠ Conflict with #8 (same file) |

### Conflict details (if any)
- **Inter-PR**: PRs #6 and #8 both modify `customer/productivity/workflows/index.mdx` — merging #6 first may affect #8
- **Git conflicts**: PR #5 has a merge conflict with main in `customer/platform/workflow-customisation.mdx`

### PR summaries
For each PR, one or two sentences from the PR body describing what changed, followed by its GitHub URL.

---

Then ask:
> Which PRs should I merge? Reply with numbers (e.g. `6 8`), `all` to merge everything, or `none` to exit without merging.

**GATE: Do not proceed until the user replies.**

---

## Phase 4 — Per-PR local preview (one PR at a time)

Work through approved PRs one at a time in ascending number order. For each PR:

### 4a — Apply locally

- If the PR is **clean** (no conflicts): apply its changes to the local working tree by cherry-picking or applying the diff from the branch.
- If the PR has **a git conflict with main** or an **inter-PR conflict**:
  - Read the current main version and the PR branch version of each conflicting file.
  - For each conflict, present a clear before/after:

    **File:** `customer/coaching/team-activity.mdx` — section "Visit Feed"

    **Current main:**
    > The Visit Feed gives you a table-based view...

    **PR proposes:**
    > Navigate to Analytics → Visit Feed...

    **My proposed resolution (and why):**
    > [resolved version] — reason: PR #3 already renamed this section; taking the PR's navigation path because it's more accurate, keeping main's filter table.

  - **GATE: Wait for the user to confirm or correct the resolution before applying anything.**

### 4b — Show the diff

Once changes are applied locally, show a per-file diff for this PR only — not a combined diff of all pending changes. Use `git diff {file}` per file rather than `git diff` across everything.

**GATE: Ask the user explicitly:**
> PR #{number} applied locally. Does this look right? Reply `yes` to merge to remote, `skip` to leave it out, or describe a correction.

**Do not proceed until the user replies.**

### 4c — Merge to remote

Once the user confirms:
1. For a **clean PR**: `gh pr merge {number} --squash --delete-branch`
2. For a **conflict-resolved PR**: commit the resolved changes, push to main, then close the PR with a comment explaining what was resolved and why.
3. `git pull` to sync local main.
4. Report: `✓ Merged PR #{number}: {title}`

Then move to the next approved PR and repeat from 4a.

---

## Phase 5 — Restore local state

1. Switch back to the original branch recorded in Phase 1: `git checkout {original-branch}`
2. If a stash was created in Phase 1, restore it: `git stash pop`
3. Report:
   > Done. Merged {n} of {total} PR(s) into main. You're back on `{original-branch}` with your local changes restored.

---

## Constraints

- Never force-push, never use `--no-verify`, never `reset --hard` without explicit user confirmation
- Never push to main or merge a PR without the user confirming the local diff first (Phase 4b gate)
- Always resolve conflicts one file at a time with explicit before/after presentation — never resolve silently
- Always merge one PR at a time — never batch-merge multiple PRs
- If any step fails unexpectedly, stop and explain before trying an alternative approach
- Writing conventions in CLAUDE.md apply when resolving content conflicts
