# DEV.tooling — IHE Devices Domain

## What This Repo Is

This is the **tooling and process hub** for the IHE Devices domain's GitHub transition. It contains:

- Planning documents and task tracking for the transition project
- Shared GitHub Actions and build scripts (once built)

## Sibling Repos

`/workspace` **is** the DEV.tooling clone. The other repos are separate clones
nested inside it, each with its own `.git` and each gitignored here.

- [DEV](https://github.com/IHE/DEV) — the domain repo: Technical Frameworks, CPs, proposals.
  **Default branch is `master`, not `main`.** Restructure work lives on `reorg`.
- [DEV.documentation](https://github.com/IHE/DEV.documentation) — playbooks, governance, onboarding guides (plain Markdown)
- [DEV.supplement-template](https://github.com/IHE/DEV.supplement-template) — template repo for new supplement documents (AsciiDoc + CI/CD)
- [DEV.MEMDMC](https://github.com/IHE/DEV.MEMDMC), [DEV.MEMLS](https://github.com/IHE/DEV.MEMLS), [DEV.POU](https://github.com/IHE/DEV.POU) — per-supplement repos, created from the template. Each publishes to GitHub Pages at `https://ihe.github.io/<repo>/`.

## Conventions

- **Repo prefix:** All Devices domain repos use the `DEV.` prefix
- **Branch strategy:** Feature branches, merge via PR. Base is `main` everywhere except `IHE/DEV`, whose default branch is `master` (deliberate — not to be renamed).
- **AsciiDoc:** Supplements are authored in AsciiDoc, rendered to HTML+PDF via CI
- **No FHIR IG tooling** in this scope
- **No CP template** — CPs are handled differently (TBD)

## Key Files

- `plan.md` — Original project spec
- `tasks.md` — Master task list (phased, prioritized)
- `repos.md` — Repository inventory
- `questions.md` — Open questions needing decisions
- `JOURNAL.md` — UADF session handoffs
