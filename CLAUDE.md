# DEV.tooling — IHE Devices Domain

## What This Repo Is

This is the **tooling and process hub** for the IHE Devices domain's GitHub transition. It contains:

- Planning documents and task tracking for the transition project
- Shared GitHub Actions and build scripts (once built)

## Sibling Repos

- [DEV.documentation](https://github.com/IHE/DEV.documentation) — playbooks, governance, onboarding guides (plain Markdown)
- [DEV.supplement-template](https://github.com/IHE/DEV.supplement-template) — template repo for new supplement documents (AsciiDoc + CI/CD)

## Conventions

- **Repo prefix:** All Devices domain repos use the `DEV.` prefix
- **Branch strategy:** Feature branches off `main`, merge via PR
- **AsciiDoc:** Supplements are authored in AsciiDoc, rendered to HTML+PDF via CI
- **No FHIR IG tooling** in this scope
- **No CP template** — CPs are handled differently (TBD)

## Key Files

- `plan.md` — Original project spec
- `tasks.md` — Master task list (phased, prioritized)
- `repos.md` — Repository inventory
- `questions.md` — Open questions needing decisions
- `JOURNAL.md` — UADF session handoffs
