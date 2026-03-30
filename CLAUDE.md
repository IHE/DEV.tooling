# DEV.tooling — IHE Devices Domain

## What This Repo Is

This is the **tooling and process hub** for the IHE Devices domain's GitHub transition. It contains:

- Planning documents and task tracking for the transition project
- Shared GitHub Actions and build scripts (once built)
- Proto-directories for repos that will be pushed to their own remotes:
  - `DEV.documentation/` — documentation (plain Markdown, rendered by GitHub)
  - `DEV.supplement-template/` — template repo for new supplement documents

## Conventions

- **Repo prefix:** All Devices domain repos use the `DEV.` prefix
- **Branch strategy:** Feature branches off `main`, merge via PR
- **AsciiDoc:** Supplements are authored in AsciiDoc, rendered to HTML+PDF via CI
- **No FHIR IG tooling** in this scope
- **No CP template** — CPs are handled differently (TBD)

## Sub-Repos

Each subdirectory under the root that starts with `DEV.` is a proto-repo. When ready, it gets:
1. A GitHub repo created by an Org Admin
2. Its contents pushed as the initial commit
3. Further development happens in its own repo

## Key Files

- `plan.md` — Original project spec
- `tasks.md` — Master task list (phased, prioritized)
- `repos.md` — Repository inventory
- `questions.md` — Open questions needing decisions
- `docs/` — Planning docs, persona guides, governance
- `JOURNAL.md` — UADF session handoffs
