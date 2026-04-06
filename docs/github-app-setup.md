# GitHub App for Automated Repo Creation

This documents how the "IHE Devices Automation" GitHub App was set up. If Org Admins for other domains want to replicate this, follow these steps.

## What It Does

When someone opens a "New Repository Request" issue on the tooling repo, a GitHub Actions workflow:

1. Generates a short-lived token from the GitHub App
2. Creates the repo from the selected template
3. Assigns the designated team as Admin
4. Comments on the issue with the new repo URL
5. Closes the issue

No personal access tokens involved — the app is tied to the org, not to any individual.

---

## Step 1: Create a GitHub App

1. Go to **Organization Settings → Developer settings → GitHub Apps → New GitHub App**
   - URL: `https://github.com/organizations/{ORG}/settings/apps/new`

2. Fill in:
   - **App name:** Something descriptive (e.g., `IHE Devices Automation`). Must be globally unique.
   - **Homepage URL:** Link to the tooling repo or any valid URL.
   - **Webhook:** Uncheck "Active" — not needed.

3. Under **Repository permissions:**
   - **Administration:** Read and write (to create repos)
   - **Contents:** Read and write (to push content)
   - **Issues:** Read and write (to comment on and close issues)
   - **Metadata:** Read-only (required, pre-selected)

4. Under **Organization permissions:**
   - **Members:** Read and write (to assign teams to repos)

5. Under **Where can this GitHub App be installed?**
   - Select **"Only on this account"**

6. Click **"Create GitHub App"**

7. Note the **App ID** shown on the settings page.

## Step 2: Generate a Private Key

1. On the app settings page, scroll to **"Private keys"**
2. Click **"Generate a private key"**
3. A `.pem` file will download — you'll need it in Step 4

## Step 3: Install the App on the Org

1. In the app settings sidebar, click **"Install App"**
2. Click **"Install"** next to your organization
3. Select **"All repositories"** (the app needs to create repos that don't exist yet)
4. Click **"Install"**

## Step 4: Store Credentials as Org Secrets

1. Go to **Organization Settings → Secrets and variables → Actions**
   - URL: `https://github.com/organizations/{ORG}/settings/secrets/actions`

2. Create two organization secrets:

   | Name | Value |
   |------|-------|
   | `DEVICES_APP_ID` | The App ID number from Step 1 |
   | `DEVICES_APP_PRIVATE_KEY` | The full contents of the `.pem` file (including BEGIN/END lines) |

3. Set repository access for both secrets (all repos, or select specific ones)

4. You can now delete the `.pem` file from your computer.

## Step 5: Create the `repo-request` Label

In the repo where the workflow will run:

1. Go to **Issues → Labels → New label**
2. Name: `repo-request`
3. Add a description and pick a color
4. Create the label

This label is what triggers the workflow — the issue form applies it automatically.

## Step 6: Add the Issue Template and Workflow

Two files are needed in the repo:

- `.github/ISSUE_TEMPLATE/new-repo-request.yml` — the issue form
- `.github/workflows/create-repo.yml` — the automation workflow

See the [DEV.tooling repo](https://github.com/IHE/DEV.tooling) for working examples of both files.

---

## Updating App Permissions

If you need to add permissions later:

1. Go to **Organization Settings → Developer settings → GitHub Apps → Edit**
2. Change permissions under **Permissions & events**
3. Click **"Save changes"**
4. Go to **Organization Settings → Integrations → Installed GitHub Apps → Configure**
5. A banner will appear asking you to **review and accept** the new permissions — approve it

The installation updates in place. No reinstall needed.

---

## Adapting for Other Domains

To replicate this for another IHE domain:

1. Either reuse the existing app (if org-wide) or create a new one following the steps above
2. Change the team name in the workflow (e.g., `dev-co-chairs` → `iti-co-chairs`)
3. Change the template name in the issue form dropdown
4. Change the repo prefix validation (e.g., `DEV.` → `ITI.`)
5. Store credentials as org secrets accessible to the new domain's tooling repo
