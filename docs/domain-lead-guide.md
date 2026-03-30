# Domain Lead Playbook — Devices Domain

> **Audience:** The technical lead(s) for the Devices domain.
> You have **Team Maintainer** status and **Admin** access to Devices repos.

---

## Your Role

Once an Org Admin creates a repo and assigns the `Devices-Domain` team, you take over.

**What you do:**
1. Manage team membership — add/remove contributors and lead authors
2. Configure new repositories — branch protection, GitHub Pages
3. Oversee the contribution workflow — PRs, reviews, merges
4. Request new repos from Org Admins when needed

**What you don't do:**
- Create repos yourself (request from Org Admin)
- Manage Org-level settings (billing, base permissions)

---

## Procedure 1: Managing the Devices Team

### Adding a Contributor

1. Go to **[github.com/orgs/IHE/teams/devices-domain/members](https://github.com/orgs/IHE/teams/devices-domain/members)**
2. Click **"Add a member"**
3. Search for their GitHub username
4. Click **"Add"** — they'll receive an invitation

> They're added as a "Member" by default. Only promote to "Maintainer" if they should also manage the team roster.

### Removing a Contributor

1. Same team page → Members
2. Find the person → click the dropdown → **Remove from team**

---

## Procedure 2: Configuring a New Repository

After the Org Admin creates a repo from a template and assigns the team, do these steps:

### 2a. Branch Protection

1. Go to repo **Settings → Branches**
2. Click **"Add branch protection rule"**
3. Branch name pattern: `main`
4. Recommended settings:
   - ☑ Require a pull request before merging
     - Require 1 approval
   - ☑ Require status checks to pass before merging
     - Select the CI build check (e.g., `build`)
   - ☑ Do not allow bypassing the above settings
5. Click **"Create"**

### 2b. Enable GitHub Pages

1. Go to repo **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: **`gh-pages`** / `/ (root)`
4. Click **"Save"**

### 2c. Update the README

The template README has placeholders. Replace them with the actual supplement name, description, and any other metadata.

---

## Procedure 3: Requesting a New Repository

When you or a Lead Author needs a new repo, email the Org Admin with:

```
Subject: New Devices Domain Repo Request

Repository name: DEV.__________
Template: DEV.template-supplement
Description: ___________________________
Lead Author GitHub username: @__________
```

The Org Admin will create the repo and assign the `Devices-Domain` team with Admin access. You'll get a confirmation email with the repo URL.

---

## Procedure 4: CI/CD — What the Template Gives You

The supplement template comes with a pre-configured GitHub Actions workflow:

- **File:** `.github/workflows/publish.yml`
- **Trigger:** Push to `main`
- **What it does:** Renders AsciiDoc → HTML + PDF → deploys to `gh-pages` branch
- **Result:** GitHub Pages serves the rendered document

### Checking Build Status

1. Go to the **Actions** tab of the repo
2. Green check = build succeeded, document published
3. Red X = build failed — click into it to read the error log

### Common CI Issues

| Problem | Fix |
|---------|-----|
| Build fails | Click the red X, read the log. Usually an AsciiDoc syntax error or missing file. |
| Pages not updating | Verify Pages is set to deploy from `gh-pages` in Settings → Pages. |

---

## Procedure 5: The Contribution Workflow You'll Enforce

### Branch Strategy

```
main (protected — no direct pushes)
 └── feature/{description}
 └── fix/{description}
 └── editorial/{description}
```

### Workflow

1. Contributor creates a branch from `main`
2. Contributor makes edits, commits, pushes
3. Contributor opens a Pull Request
4. CI builds automatically — checks the PR
5. You or a reviewer reviews the PR
6. After approval + CI green → merge to `main`
7. CI auto-publishes the updated document

---

## Quick Reference

| Task | URL |
|------|-----|
| Manage team | `github.com/orgs/IHE/teams/devices-domain/members` |
| Repo settings | `github.com/IHE/{repo}/settings` |
| Branch protection | `github.com/IHE/{repo}/settings/branches` |
| GitHub Pages | `github.com/IHE/{repo}/settings/pages` |
| CI/CD runs | `github.com/IHE/{repo}/actions` |
