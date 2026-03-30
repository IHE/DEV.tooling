# Devices Domain GitHub Transition — Master Task List

## Legend
- **P0** = Must have before anyone can start working
- **P1** = Needed for full workflow, follows shortly after
- **P2** = Future / nice-to-have

---

## Phase 1: Foundation (P0)

### Org-Level Setup (Org Admins do these)
- [ ] Set repository creation to "Owners Only" (Org Settings → Member privileges → Repository creation → None)
- [ ] Set default repository permissions to "Read" (Org Settings → Member privileges → Base permissions)
- [ ] Decide: public or private repos? (TBD — document the decision when made)

### Team Setup
- [ ] Create `Devices-Domain` GitHub Team (Org Settings → Teams → New team)
- [ ] Add Domain Lead(s) to the team and promote to **Maintainer**
- [ ] Add initial contributors as team Members
- [ ] Document the team roster in the playbooks repo

### Template: `DEV.supplement-template`
- [ ] Create the repo in the IHE org
- [ ] Set up directory structure for AsciiDoc supplements (see below)
- [ ] Create `.github/workflows/publish.yml` — AsciiDoc → HTML + PDF → `gh-pages`
- [ ] Add `README.md` with placeholder tokens for supplement name, status, etc.
- [ ] Add `CONTRIBUTING.md` with Devices domain contribution guidelines
- [ ] Add `.github/PULL_REQUEST_TEMPLATE.md`
- [ ] Check "Template repository" in repo Settings → General
- [ ] Test: create a repo from the template, push a change, verify it builds and publishes
- [ ] Decide on license (TO DO — deferred)

### Tooling: `DEV.tooling`
- [ ] Create the repo
- [ ] Build reusable GitHub Action for AsciiDoc → HTML + PDF rendering
- [ ] Include any shared scripts or build helpers
- [ ] Document how templates consume the shared action

---

## Phase 2: Documentation & Governance (P1)

### Playbooks: `DEV.documentation`
- [ ] Create the repo
- [ ] Enable GitHub Pages with Jekyll (Settings → Pages → Source: branch `main`, folder `/ (root)` or `/docs`)
- [ ] Set up minimal Jekyll config (`_config.yml` with title and theme)
- [ ] Write and publish the following guides:
  - [ ] **Org Admin Playbook** (how to create repos, assign teams)
  - [ ] **Domain Lead Playbook** (how to manage teams, configure repos)
  - [ ] **Contributor / Lead Author Guide** (how to write, branch, PR, get published)
  - [ ] **Reviewer Guide** (how to review PRs)
- [ ] Stub out governance sections:
  - [ ] Decision-making process
  - [ ] Roles and responsibilities summary
  - [ ] Document lifecycle (draft → public comment → trial implementation → final text)
  - [ ] Naming conventions
  - [ ] Archival and versioning policy
  - [ ] Offboarding / succession plan
- [ ] Add a "How to Edit These Playbooks" page (so anyone can update the docs)

### Repo Request Process
- [ ] Write up the email request template (what info the Domain Lead needs to provide)
- [ ] Document step-by-step what the Org Admin does when they receive the request
- [ ] Include this in the Org Admin Playbook

---

## Phase 3: Operational Readiness (P1)

### CI/CD Validation
- [ ] Test the AsciiDoc publish workflow end-to-end with real content
- [ ] Verify GitHub Pages serves the rendered output correctly
- [ ] Set up caching in GitHub Actions (Ruby gems for Asciidoctor) for faster builds

### Pilot
- [ ] Create one real supplement repo from the template
- [ ] Have a lead author make a real edit via PR
- [ ] Review and merge the PR
- [ ] Verify the published output on GitHub Pages
- [ ] Collect feedback and iterate

---

## Phase 4: Future / Nice-to-Have (P2)

- [ ] Decide on and add a license to templates
- [ ] Domain verification for custom subdomains (`devices.ihe.net` or similar)
- [ ] DNS CNAME setup if custom subdomain is desired
- [ ] AsciiDoc theming / IHE branding for rendered documents
- [ ] White papers repo (if needed)
- [ ] Link checker GitHub Action in templates
- [ ] Spell checker / vale linter for AsciiDoc content
- [ ] Automated repo creation via GitHub Issues (eliminates email step)
- [ ] Badge/status page showing which supplements are published
- [ ] Training recordings for each persona
- [ ] Audit logging guidance
- [ ] Billing documentation (GitHub Free limits, when to consider upgrading)
