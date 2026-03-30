# Org Admin Playbook — Devices Domain

> **Audience:** Non-technical IHE staff with GitHub "Owner" access on the IHE org.
> Everything here uses the GitHub web interface. No code, no command line.

---

## Your Role

You are the **gatekeeper for new repositories**. Domain Leads and Lead Authors can't create repos themselves — they request them through you.

**What you do:**
1. Create new repositories from templates when requested
2. Assign the `Devices-Domain` team with Admin access to those repos
3. Confirm back to the requester

**What you don't do:**
- Manage who is on the Devices team (that's the Domain Lead's job)
- Configure CI/CD, branch protection, or any technical settings (baked into the template)
- Write or review document content

---

## Procedure: Handling a New Repository Request

### What You'll Receive (via Email)

A Domain Lead or Lead Author will send you a request containing:

| Field | Example | Required? |
|-------|---------|-----------|
| **Repository name** | `DEV.wia` | Yes |
| **Which template to use** | `DEV.template-supplement` | Yes |
| **Short description** | "WIA Supplement for Devices" | Yes |
| **Lead Author GitHub username** | `@janedoe` | Yes |

### Step 1: Create the Repository

1. Go to **[github.com/organizations/IHE/repositories/new](https://github.com/organizations/IHE/repositories/new)**

2. Under **"Repository template"**, select the template from the request
   - For supplements: `IHE/DEV.template-supplement`

3. Fill in:
   - **Owner:** `IHE`
   - **Repository name:** the name from the request (e.g., `DEV.wia`)
   - **Description:** the short description from the request
   - **Visibility:** *(follow current policy — TBD)*
   - **Check** ☑ "Include all branches"

4. Click **"Create repository"**

### Step 2: Assign the Devices Team

1. In the new repo, go to **Settings → Collaborators and teams**
   - Direct URL: `github.com/IHE/{repo-name}/settings/access`

2. Click **"Add teams"**

3. Search for **`Devices-Domain`**

4. Set the role to **"Admin"**

5. Click **"Add"**

### Step 3: Confirm

Reply to the requester with:
- The repo URL: `https://github.com/IHE/{repo-name}`
- Confirmation that the `Devices-Domain` team has Admin access
- Remind them they can now manage settings and contributors themselves

---

## Procedure: Creating the Devices Team (One-Time Setup)

> You only need to do this once.

1. Go to **[github.com/orgs/IHE/new-team](https://github.com/orgs/IHE/new-team)**
2. **Team name:** `Devices-Domain`
3. **Description:** "IHE Devices domain team"
4. **Visibility:** Visible
5. Click **"Create team"**
6. **Add the Domain Lead:** Team page → Members → "Add a member" → search by username → Add
7. **Promote to Maintainer:** Find them in the Members list → click the role dropdown → change to **"Maintainer"**

> "Maintainer" lets the Domain Lead add/remove team members on their own.

---

## Email Request Template

Share this with Domain Leads so they know what to send you:

```
Subject: New Devices Domain Repo Request

To: [Org Admin email]

Please create a new repository with the following details:

  Repository name: DEV.__________
  Template: DEV.template-supplement
  Description: ___________________________
  Lead Author GitHub username: @__________

Thank you!
```

---

## Quick Reference

| Template | When to use |
|----------|-------------|
| `DEV.template-supplement` | New supplement document |

---

## Troubleshooting

**"I can't find the template in the dropdown"**
→ The template repo might not have "Template repository" checked. Ask the Domain Lead to verify in that repo's Settings → General.

**"The requester says they can't change repo settings"**
→ Check that you assigned the `Devices-Domain` team with the **Admin** role, not Write or Maintain.

**"Someone asks me to add them to the Devices team"**
→ Redirect them to the Domain Lead. You only manage Org-level things, not team membership.
