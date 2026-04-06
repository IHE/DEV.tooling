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
