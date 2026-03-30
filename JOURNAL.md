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
