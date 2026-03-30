# Devices Domain — Governance

> This document outlines the governance framework for the IHE Devices domain's GitHub presence.
> Sections marked **(TBD)** need to be filled in as decisions are made.

---

## Roles and Responsibilities

| Role | Who | Permissions | Responsibilities |
|------|-----|-------------|-----------------|
| **Org Admin** | IHE staff (non-technical) | GitHub Org Owner | Create repos from templates, assign teams, DNS/domain setup |
| **Domain Lead** | Devices domain technical lead | Team Maintainer + Repo Admin | Manage team membership, configure repos, oversee workflows |
| **Lead Author** | Owner of a specific supplement or document | Team Member + write access | Coordinate contributions, review PRs, manage document lifecycle |
| **Contributor** | Anyone writing or editing content | Team Member + write access | Create branches, submit PRs, respond to review feedback |
| **Reviewer** | Anyone reviewing content | Team Member (read access minimum) | Review PRs, provide technical feedback, approve or request changes |

---

## Decision-Making

**(TBD)** — How are decisions made for the Devices domain's GitHub workflow?

- Who decides whether to create a new repo vs. add to an existing one?
- Who approves changes to the templates or CI/CD workflows?
- Who resolves disagreements about document content?
- How do decisions get documented and communicated?

---

## Document Lifecycle

IHE documents typically move through these stages:

| Stage | Description | GitHub Representation |
|-------|-------------|----------------------|
| **Draft** | Initial authoring, not yet public | Work happens on branches; PRs merged to `main` |
| **Public Comment** | Published for community review | **(TBD)** — tag/release? separate branch? |
| **Trial Implementation** | Approved for trial use | **(TBD)** — tag/release? |
| **Final Text** | Officially published | **(TBD)** — tag/release? |

**(TBD):** How does the document lifecycle map to GitHub features?
- Do we use GitHub Releases to mark lifecycle transitions?
- Do we use tags (e.g., `v1.0-public-comment`, `v2.0-final-text`)?
- Do we use branches for different lifecycle stages?
- How does the published output reflect the current stage?

---

## Naming Conventions

### Repositories

All Devices domain repos use the `DEV.` prefix:

```
DEV.{document-name}
```

Examples: `DEV.wia`, `DEV.sdpi`, `DEV.playbooks`, `DEV.tooling`

### Branches

```
feature/{description}  — new content
fix/{description}      — corrections
editorial/{description} — formatting, typos
```

### Commits

Use imperative mood, describe what was done:
- "Add actor definitions for Device Observer"
- "Fix table numbering in section 3.2"

---

## Repository Request Process

1. Domain Lead or Lead Author identifies the need for a new repo
2. They email the Org Admin with:
   - Repository name (`DEV.{name}`)
   - Which template to use (`DEV.supplement-template`)
   - Short description
   - Lead Author's GitHub username
3. Org Admin creates the repo from the template
4. Org Admin assigns the `Devices-Domain` team as Admin
5. Org Admin confirms back via email with the repo URL
6. Domain Lead configures branch protection and repo settings

---

## Archival and Versioning

**(TBD)** — What happens to repos when a document is finalized?

- Are repos archived (read-only)?
- Are final documents tagged with a version?
- Where is the canonical published version hosted?
- How long are draft/working repos kept active?

---

## Offboarding and Succession

**(TBD)** — What happens when key people leave?

- Who takes over if the Domain Lead steps down?
- How is institutional knowledge preserved? (Answer: in this playbooks repo)
- Who has Org Owner access, and is there a backup?
- What happens at the end of the project lead's term?

---

## Security and Access

**(TBD)** — Baseline security posture:

- Are repos public or private? (Decision pending)
- Are signed commits required?
- Who can merge to `main`? (Currently: anyone with write access + PR approval)
- Are there any secrets or credentials that need rotation?

---

## Audit and Compliance

**(TBD)** — What audit trail is needed?

- GitHub Free provides limited audit logging
- PR history provides a full change log for all documents
- Team membership changes are visible in the team activity log
- If more audit capability is needed, GitHub Enterprise may be required

---

## Open Questions

- [ ] Public vs. private repos
- [ ] License for document content
- [ ] CP workflow (handled outside templates — TBD)
- [ ] Document lifecycle → GitHub features mapping
- [ ] Archival policy for completed documents
- [ ] Succession plan for key roles
