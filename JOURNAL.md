# JOURNAL — dev-tooling

Project log and session handoffs for the IHE Devices Domain GitHub transition.

---

## Session Handoff - 2026-03-30 (Session 0 — Bootstrapping)

### Completed This Session
- Created initial planning documents from project spec (`plan.md`)
- Scoped project down to **Devices domain only** (no ITI, PCC, FHIR IG)
- Built repository inventory (`repos.md`)
- Built phased task list (`tasks.md`)
- Wrote persona playbooks:
  - Org Admin guide (`docs/org-admin-guide.md`)
  - Domain Lead guide (`docs/domain-lead-guide.md`)
  - Contributor/Lead Author guide (`docs/contributor-guide.md`)
  - Reviewer guide (`docs/reviewer-guide.md`)
- Stubbed out governance framework (`docs/governance.md`)
- Dropped CP template from scope
- Initialized git repo, set up UADF, restructured as `dev-tooling`
- Created proto-directories: `dev-playbooks/`, `dev-template-supplement/`

### Current State
- Branch: `main`
- No remote configured yet (user will create GitHub repo and provide URL)
- Meeting with Org Admins, Domain Leads, and Lead Authors scheduled for 2026-03-31 morning

### Next Steps
1. User provides GitHub remote URL → push initial commit
2. Scaffold `dev-playbooks/` as a Jekyll site (simple Markdown, GitHub Pages)
3. Scaffold `dev-template-supplement/` (need supplement AsciiDoc structure — see Q2 in questions.md)
4. Build the AsciiDoc CI/CD workflow (GitHub Actions)
5. Update `repos.md` and `tasks.md` to reflect dropped CP template

### Open Questions / Blockers
- Supplement AsciiDoc structure unknown — need a reference or description (questions.md Q2)
- Repo naming prefix: `dev-` vs `devices-` vs `DEV-` (questions.md Q3)
- Public vs. private repos (TBD)
- CP workflow still undefined (no longer blocking — no template needed)

---

## Session Handoff - 2026-03-30 (Session 1 — Repos Live)

### Completed This Session
- Created all three GitHub repos and pushed initial content:
  - **DEV.tooling** (https://github.com/IHE/DEV.tooling) — planning docs, task list, persona guides, governance stubs
  - **DEV.documentation** (https://github.com/IHE/DEV.documentation) — plain Markdown documentation site with nav links
  - **DEV.supplement-template** (https://github.com/IHE/DEV.supplement-template) — AsciiDoc template with CI/CD workflow, marked as template repo
- Standardized naming convention to `DEV.{name}` (dot separator, uppercase prefix)
- Discovered GitHub Pages requires a paid org plan — pivoted:
  - DEV.documentation: stripped Jekyll, now plain Markdown rendered natively by GitHub
  - DEV.supplement-template: CI produces downloadable HTML+PDF artifacts instead of Pages deployment
- Scaffold supplement template with IHE volume structure (Vol 1: Integration Profiles, Vol 2: Transactions, Vol 3: Content Modules)
- Built GitHub Actions workflow for AsciiDoc → HTML + PDF build
- Added Makefile for local preview (native asciidoctor or Docker)
- Added PR template, issue template, contributing guide to supplement template
- Removed all GitHub Pages references across all three repos
- User marked DEV.supplement-template as a template repository in GitHub settings

### Current State
- Branch: `main` (all three repos)
- All repos pushed and up to date with remotes
- DEV.tooling: 4 commits, last: `7c11c69 Remove all GitHub Pages references`
- DEV.documentation: 3 commits, last: `2c405f1 Remove Jekyll, use plain Markdown`
- DEV.supplement-template: 2 commits, last: `5f9d94f Remove Jekyll, use plain Markdown`
- Clean working trees on all three repos

### Next Steps
1. **User is reviewing all documentation** — will take notes on needed changes (small and large)
2. Apply user's feedback/edits from the review
3. Validate the CI workflow actually runs on GitHub (first push to a repo created from the template)
4. Pilot: create a real supplement repo from the template and test the full workflow
5. Finalize supplement AsciiDoc structure based on user's knowledge of IHE conventions

### Open Questions / Blockers
- Supplement AsciiDoc structure is a best-guess based on IHE conventions — user may want significant changes after review
- Repo naming prefix settled as `DEV.` but user hasn't confirmed for supplement working repos specifically (e.g., `DEV.wia` vs something else)
- Public vs. private repos still TBD
- License still deferred
- CI workflow not yet validated on GitHub Actions (will fire on first real push to a repo created from template)

### Relevant Context
- GitHub Free org plan: no Pages, no custom roles, no sub-organizations. All solutions must work within these constraints.
- The `docs/` directory in DEV.tooling contains copies of persona guides that predate the DEV.documentation versions. The DEV.documentation versions are the canonical ones now. The DEV.tooling copies could be removed or marked as drafts to avoid confusion.
- Container environment has no Ruby — can't test AsciiDoc builds locally. CI validation will happen on GitHub.
- Meeting with Org Admins, Domain Leads, and Lead Authors is morning of 2026-03-31.

---

## Session Handoff - 2026-04-02 (Session 2 — Repo Cleanup)

### Completed This Session
- Established branch and repo policies:
  - **Working repos** (DEV, DEV.PCIM, DEV.SDPi): only work on branches, never main. Use `reorg` as branch name for reorganization work.
  - **New project repos** (DEV.tooling, DEV.documentation, DEV.supplement-template): can commit directly to main.
  - **sdpi-fhir**: hands-off, included for reference only. May revisit based on group feedback.
- Merged richer governance content from DEV.tooling into DEV.documentation:
  - Document lifecycle table with "GitHub Representation" column
  - Commit message conventions
  - Expanded repository request process (4 → 6 steps)
  - Detailed TBD questions for archival, offboarding, security sections
  - New "Audit and Compliance" section
  - Commit: `3113c96 Merge richer governance content from DEV.tooling`
- Cleaned up DEV.tooling — removed duplicate `docs/` directory (5 files):
  - Updated CLAUDE.md to reference sibling repos instead of proto-directories
  - Updated overview.md with accurate directory structure and status
  - Commit: `8526356 Remove docs/ directory, update references`
- Both repos pushed to GitHub
- Set up git identity (Michael Faughn / michael.faughn@nist.gov)

### Current State
- Branch: `main` (all repos)
- All repos pushed and up to date with remotes
- DEV.tooling: 5 commits, last: `8526356 Remove docs/ directory, update references`
- DEV.documentation: 4 commits, last: `3113c96 Merge richer governance content from DEV.tooling`
- DEV.supplement-template: 2 commits, unchanged this session
- Clean working trees on all repos
- Local clones of working repos (DEV, DEV.PCIM, DEV.SDPi, sdpi-fhir) in `/workspace/iheDev/` — untouched

### Next Steps
1. User reviews updated governance and tooling docs on GitHub
2. Apply any feedback from user's review
3. Validate the CI workflow on GitHub Actions (still not tested)
4. Pilot: create a real supplement repo from the template and test end-to-end
5. Study DEV.SDPi and DEV.PCIM AsciiDoc structures to inform the supplement template
6. Consider what `reorg` branch work is needed on the working repos

### Open Questions / Blockers
- Supplement AsciiDoc structure still best-guess — DEV.SDPi and DEV.PCIM exist as real-world references now
- Public vs. private repos still TBD
- License still deferred
- CI workflow not yet validated on GitHub Actions
- No `reorg` work scoped yet for the working repos (DEV, DEV.PCIM, DEV.SDPi)

### Relevant Context
- Workspace layout: `/workspace/ihe_git/` has the JOURNAL and planning docs; `/workspace/iheDev/` has the actual repo clones
- The `ihe_git` directory is NOT a git repo — it's a local working area for project management files
- DEV.SDPi is the most mature AsciiDoc supplement (~500+ PRs) and is the best reference for template structure
- DEV.PCIM is a smaller supplement with PDF backend enabled
- sdpi-fhir is a FHIR IG companion — old, not actively used, kept for reference only

---

## Session Handoff - 2026-04-06 (Session 3 — Automation & Theming)

### Completed This Session

**Automated repo creation via GitHub Issues:**
- Created a GitHub App ("IHE Devices Automation") for the IHE org with repo creation, team management, and issues permissions
- Built issue form template (`.github/ISSUE_TEMPLATE/new-repo-request.yml`) and workflow (`.github/workflows/create-repo.yml`) in DEV.tooling
- Debugged several issues during setup:
  - `repo-request` label must exist in the repo before the form can apply it
  - Initial third-party issue body parser (`peter-murray/issue-forms-body-parser`) broke — replaced with simple `awk` parsing
  - GitHub App needed Issues Read/Write permission added and accepted via installation settings
  - Bumped `actions/create-github-app-token` to v2 for Node.js compat
- Successfully tested end-to-end: issue opened → repo created → team assigned → comment posted → issue closed
- Documented the full GitHub App setup process in `docs/github-app-setup.md` in DEV.tooling

**DEV.documentation updates:**
- Restructured Org Admin playbook: automation is primary, manual is fallback
  - New page: `org-admin-manual-repo-creation.md` (the old manual procedure)
  - New page: `org-admin-github-app.md` (app maintenance, permissions, key rotation)
- Updated Domain Lead playbook: reordered procedures (request → configure), updated CI/CD section, added reference links
- Updated Contributor guide: repo requests point to issue form
- Updated Governance: repo request process reflects automated + fallback flow
- Updated all references from `src/` to `AsciiDoc_Source/` (user renamed on GitHub)
- Added Technical Reference section:
  - `reference/theming.md` — how shared and per-repo CSS/PDF themes work
  - `reference/build-system.md` — how CI builds HTML+PDF, downloading artifacts, local preview

**Shared theming infrastructure:**
- Created `theme/` directory in DEV.tooling with placeholder files:
  - `ihe-base.css` — shared HTML stylesheet
  - `ihe-base-theme.yml` — shared PDF theme (page layout, fonts, headers/footers)
- Updated supplement template workflow to fetch theme from DEV.tooling at build time
- Added `AsciiDoc_Source/theme/custom.css` placeholder in supplement template for per-repo additive styling (true cascading, not replacement)

**CI/CD validation:**
- Supplement template build workflow confirmed working on GitHub Actions
- Fixed path issue when user renamed `src/` to `AsciiDoc_Source/`

### Current State
- Branch: `main` (all three repos)
- All repos pushed and up to date with remotes
- DEV.tooling: last commit `d4e13b0 Add shared theme files for AsciiDoc publications`
- DEV.documentation: last commit `5628202 Revise domain lead playbook`
- DEV.supplement-template: last commit `6367eec Add shared theme support to build workflow`
- Clean working trees on all repos
- GitHub App installed and working on IHE org
- CI/CD build passing on DEV.supplement-template

### Next Steps
1. User continues reviewing documentation for accuracy
2. Populate IHE branding in theme files (logo, colors, fonts) when assets are available
3. Pilot: create a real supplement repo from the template and test end-to-end workflow with actual content
4. Consider automating branch protection setup for new repos (currently manual per Procedure 3a in Domain Lead playbook)
5. Update `tasks.md` and `repos.md` in DEV.tooling to reflect completed work
6. Clean up stale planning docs that have been superseded by DEV.documentation

### Open Questions / Blockers
- Public vs. private repos still TBD
- License still deferred
- Branch protection can't be baked into GitHub templates — must be set manually per repo (or automated via a separate workflow)
- The `docs/` directory was removed from DEV.tooling in Session 2 but the planning files (`tasks.md`, `repos.md`, `questions.md`, `overview.md`) are getting stale — many items are now complete
- PDF theme `custom-theme.yml` per-repo override is documented but not yet wired into the workflow (only CSS cascading is implemented)

### Relevant Context
- GitHub Free org plan constraints are well-understood now: no Pages, no custom roles, no sub-orgs. All solutions work within these limits.
- The GitHub App uses org-level secrets (`DEVICES_APP_ID`, `DEVICES_APP_PRIVATE_KEY`) — accessible to all repos in the org
- User renamed `src/` to `AsciiDoc_Source/` and restructured the supplement template on GitHub directly — removed volume files, added CP directories
- The `peter-murray/issue-forms-body-parser` action is unreliable — we use raw `awk` parsing of the issue body instead, which is simpler and has no dependencies
- The `create-github-app-token` action v2 still triggers a Node.js 20 deprecation warning but works fine
