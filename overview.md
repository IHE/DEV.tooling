# DEV.tooling — Workspace Overview

## What This Repo Is

This is the `DEV.tooling` repo for the IHE Devices domain GitHub transition. It serves as:
1. **Process documentation** — planning, task tracking, decision records
2. **Shared tooling** — GitHub Actions, build scripts (once built)
3. **Proto-repos** — subdirectories that will become their own GitHub repos when ready

## Scope

**Devices domain only.** No ITI, PCC, FHIR IG, or AsciiDoc theming.

---

## Directory Structure

```
/workspace (DEV.tooling)
├── CLAUDE.md                    # Project instructions
├── JOURNAL.md                   # Session handoffs (UADF)
├── plan.md                      # Original project spec
├── tasks.md                     # Master task list (phased, prioritized)
├── repos.md                     # Repository inventory
├── questions.md                 # Open questions needing decisions
├── overview.md                  # This file
│
├── docs/                        # Planning docs & persona guides
│   ├── org-admin-guide.md       # Org Admin playbook
│   ├── domain-lead-guide.md     # Domain Lead playbook
│   ├── contributor-guide.md     # Contributor / Lead Author guide
│   ├── reviewer-guide.md        # Reviewer guide
│   ├── governance.md            # Governance framework (stubbed)
│   └── adr/                     # Architecture Decision Records
│
├── DEV.documentation/               # Proto-repo: Jekyll site for docs
│   └── (to be scaffolded)
│
└── DEV.supplement-template/     # Proto-repo: supplement template
    └── (to be scaffolded)
```

## Status

| Item | Status |
|------|--------|
| Planning docs | Done |
| Persona playbooks (4) | Done |
| Governance stubs | Done |
| Git repo initialized | Done |
| UADF set up | Done |
| Remote configured | Waiting for user to create GitHub repo |
| `DEV.documentation/` scaffolded | Not started |
| `DEV.supplement-template/` scaffolded | Blocked on supplement structure (Q1) |
| CI/CD workflow YAML | Not started |
