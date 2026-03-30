# Reviewer Guide — Devices Domain

> **Audience:** Anyone reviewing Pull Requests on Devices domain repos.

---

## How to Review a Pull Request

### 1. Find the PR

You'll either get a notification (email or GitHub) or browse: repo → **Pull Requests** tab → open PRs.

### 2. Understand the Change

- Read the **PR description** — the author explains what changed and why
- Click the **"Files changed"** tab to see exactly what was added, removed, or modified
- Check the **CI status** at the bottom of the PR — if it's red, the author needs to fix build errors first

### 3. Leave Comments

On the "Files changed" tab:
1. Hover over a line number → click the blue **`+`**
2. Write your comment
3. To suggest an exact fix, use:

````markdown
```suggestion
The corrected text goes here.
```
````

The author can accept your suggestion with one click.

### 4. Submit Your Review

Click **"Review changes"** (green button, top-right of Files changed):
- **Approve** — changes look good
- **Request changes** — something needs to be fixed
- **Comment** — general feedback, neither approval nor rejection

---

## What to Check

- [ ] Content is technically accurate
- [ ] Consistent with IHE conventions and terminology
- [ ] Cross-references and includes are correct
- [ ] Tables and diagrams render properly (CI should catch syntax issues)
- [ ] Changes match the stated scope — no unrelated edits

---

## Tips

- **Be specific** — point to exact lines, suggest alternatives
- **Mark severity** — prefix blocking issues with `[BLOCKING]`, minor suggestions with `[NIT]`
- **Respond within 2–3 business days** if possible
- If you don't understand a change, **ask questions** rather than approving blindly
