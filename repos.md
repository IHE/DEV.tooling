# Devices Domain — Repository Inventory

## Expected Total: 7–13 repos (low teens over time)

---

## Template Repositories

| Repo Name | Purpose | Status |
|-----------|---------|--------|
| `DEV.template-supplement` | Template for new Supplement documents (AsciiDoc + CI/CD) | To build |

> Must have **"Template repository"** checked in Settings → General.

---

## Supporting Repositories

| Repo Name | Purpose | Notes |
|-----------|---------|-------|
| `DEV.documentation` | Documentation, governance, onboarding guides. Hosted at GitHub Pages. | The "how everything works" hub. Built with Jekyll (GitHub's built-in static site — just push Markdown). |
| `DEV.tooling` | Planning docs, shared GitHub Actions, Asciidoctor build scripts, reusable workflows. Also contains proto-directories for other repos during bootstrapping. | Referenced by template workflows via `uses: IHE/DEV.tooling/...` |

---

## Working Repositories

| Repo Name | Purpose | Status |
|-----------|---------|--------|
| *(existing TF repo)* | Devices Technical Framework (already exists) | No migration needed |
| `DEV.{supplement-name}` | Individual supplement repos, created from `DEV.template-supplement` | Created on demand |
| `DEV.whitepapers` | White papers (maybe) | TBD |

---

## Naming Convention

```
DEV.{name}
```

**Examples:**
- `DEV.template-supplement` — the supplement template
- `DEV.wia` — a supplement called "WIA"
- `DEV.sdpi` — a supplement called "SDPi"
- `DEV.documentation` — the documentation site

---

## What's NOT in Scope

- No FHIR IG template or tooling
- No CP template — CPs will be handled differently (TBD)
- No Technical Framework template (the TF repo already exists)
- No repos for other IHE domains (ITI, PCC, RAD, etc.)
- No automated repo creation workflows
- No AsciiDoc theming (for now)
