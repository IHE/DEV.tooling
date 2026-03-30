# Contributor & Lead Author Guide — Devices Domain

> **Audience:** Authors, editors, and lead authors who write and review IHE Devices domain documents on GitHub.

---

## Getting Started

### What You Need

1. **A GitHub account** — [github.com/signup](https://github.com/signup)
2. **Git installed** — [git-scm.com/downloads](https://git-scm.com/downloads)
3. **A text editor** — [VS Code](https://code.visualstudio.com/) recommended, with the "AsciiDoc" extension
4. **Team access** — ask the Devices Domain Lead to add you

### One-Time Setup

```bash
# Set your identity (use the same email as your GitHub account)
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Clone the repo you'll work on
git clone https://github.com/IHE/DEV.{supplement-name}.git
cd DEV.{supplement-name}
```

---

## How to Make Changes

### Step 1: Get the Latest Code

```bash
git checkout main
git pull
```

### Step 2: Create a Branch

Never edit `main` directly. Always work on a branch.

```bash
git checkout -b feature/add-actor-definitions
```

Name your branch descriptively:
- `feature/add-section-3` — new content
- `fix/correct-table-4-1` — fixing an error
- `editorial/typo-fixes` — formatting and typos

### Step 3: Edit the AsciiDoc Files

Open the `.adoc` files in the `src/` directory with your text editor. Make your changes.

### Step 4: Save and Commit

```bash
# Stage the files you changed
git add src/section-3.adoc

# Commit with a clear message
git commit -m "Add actor definitions for Device Observer"
```

Write commit messages that explain **what** you did:
- "Add transaction diagram for DEV-01"
- "Fix incorrect OID in Table 3.1-1"
- "Update conformance statement per CP-42"

### Step 5: Push Your Branch

```bash
git push -u origin feature/add-actor-definitions
```

### Step 6: Open a Pull Request

1. Go to the repo on GitHub
2. You'll see a banner: "feature/add-actor-definitions had recent pushes" → click **"Compare & pull request"**
3. Fill in a title and description explaining your changes
4. Click **"Create pull request"**

### Step 7: Wait for Review

- The CI system will automatically build your changes
- A reviewer will look at your PR and may leave comments
- If changes are requested, edit the same branch, commit, and push — the PR updates automatically:

```bash
git add src/section-3.adoc
git commit -m "Address review: clarify actor responsibilities"
git push
```

### Step 8: Merge

Once approved and CI passes, the PR gets merged. The document is automatically rebuilt and published.

---

## For Lead Authors: Additional Responsibilities

As a Lead Author, you are the primary owner of a specific supplement or document. Beyond the contributor workflow above, you also:

1. **Coordinate contributions** — decide who works on what sections
2. **Review PRs** — you're the first reviewer for changes to your document
3. **Manage the document lifecycle** — track status (draft, public comment, trial implementation, final text)
4. **Request the repo** — when starting a new supplement, email the Org Admin (or ask the Domain Lead to) with:
   - Repository name: `DEV.{supplement-name}`
   - Template: `DEV.supplement-template`
   - Description: one-liner about the supplement
   - Your GitHub username

---

## AsciiDoc Quick Reference

### Headings

```asciidoc
= Document Title (Level 0 — used once)
== Chapter (Level 1)
=== Section (Level 2)
==== Subsection (Level 3)
```

### Text Formatting

```asciidoc
*bold*
_italic_
`monospace`
```

### Lists

```asciidoc
* Bullet point
** Nested bullet

. Numbered item
.. Nested number
```

### Tables

```asciidoc
[cols="1,2,3", options="header"]
|===
| Column 1 | Column 2 | Column 3
| Cell     | Cell     | Cell
|===
```

### Cross-References

```asciidoc
// Create an anchor
[[my-section-id]]
=== My Section

// Reference it
See <<my-section-id>> for details.
```

### Include Another File

```asciidoc
\include::chapter-1.adoc[]
```

### Images

```asciidoc
image::images/diagram.png[Alt text]
```

### Notes and Warnings

```asciidoc
NOTE: This is a note.

WARNING: This is a warning.

TIP: This is a tip.
```

---

## Troubleshooting

**"Permission denied" when pushing**
→ The Domain Lead may not have added you to the team yet. Ask them.

**"Your branch is behind main"**
```bash
git checkout main
git pull
git checkout your-branch
git merge main
# Fix any conflicts, then commit and push
```

**"CI check failed on my PR"**
→ Click the red X on your PR to see the build log. Usually an AsciiDoc syntax error or missing file.

**"I accidentally committed to main"**
→ If branch protection is on, you can't push to main anyway. Ask the Domain Lead for help if you need to fix your local setup.

---

## Getting Help

- **Git/GitHub questions:** Ask the Domain Lead
- **Content questions:** Discuss in the PR comments
- **Template or build issues:** File an issue on the `DEV.tooling` repo
