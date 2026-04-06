# IHE Devices Domain — Shared Theme

These theme files are applied to all Devices domain AsciiDoc publications at build time.

## Files

| File | Purpose |
|------|---------|
| `ihe-base.css` | HTML stylesheet — controls how rendered HTML documents look |
| `ihe-base-theme.yml` | PDF theme — controls fonts, colors, layout, headers/footers in PDF output |

## How It Works

Each supplement repo's CI workflow checks out this directory from DEV.tooling at build time. The base theme is applied first, then any per-repo customizations are layered on top.

### Per-repo customization

Individual repos can add a `AsciiDoc_Source/theme/custom.css` (for HTML) or `AsciiDoc_Source/theme/custom-theme.yml` (for PDF). These are **additive** — they cascade on top of the base theme, they don't replace it.

## Updating

Edit the files here in DEV.tooling. The next time any supplement repo builds, it will pick up the changes automatically.
