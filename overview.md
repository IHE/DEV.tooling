# DEV.tooling — Workspace Overview

## What This Repo Is

This is the `DEV.tooling` repo for the IHE Devices domain GitHub transition. It serves as:
1. **Process documentation** — planning, task tracking, decision records
2. **Shared tooling** — GitHub Actions, build scripts (once built)

## Scope

**Devices domain only.** No ITI, PCC, FHIR IG, or AsciiDoc theming.

---

## Sibling Repos

Playbooks, governance, and onboarding guides live in [DEV.documentation](https://github.com/IHE/DEV.documentation).
The supplement template lives in [DEV.supplement-template](https://github.com/IHE/DEV.supplement-template).

## Directory Structure

```
DEV.tooling/
├── CLAUDE.md         # Project instructions
├── JOURNAL.md        # Session handoffs (UADF)
├── plan.md           # Original project spec
├── tasks.md          # Master task list (phased, prioritized)
├── repos.md          # Repository inventory
├── questions.md      # Open questions needing decisions
└── overview.md       # This file
```

## Status

| Item | Status |
|------|--------|
| Planning docs | Done |
| Persona playbooks (4) | Done — in DEV.documentation |
| Governance stubs | Done — in DEV.documentation |
| Git repo initialized | Done |
| UADF set up | Done |
| Repos live on GitHub | Done |
| CI/CD workflow YAML | Not yet validated on GitHub Actions |
