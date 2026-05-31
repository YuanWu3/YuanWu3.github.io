# al-folio Migration Overlay for YuanWu3.github.io

This branch migrates the current single-page academic homepage to an al-folio-based GitHub Pages workflow.

## Design

The repository keeps a lightweight `al-folio-overlay/` directory with Yuan Wu's customized content. During deployment, GitHub Actions clones the upstream `alshedivat/al-folio` theme, overlays this content, builds the Jekyll site, and deploys the generated `_site` directory to GitHub Pages.

This avoids copying the full al-folio codebase into the personal homepage repository and makes future upstream updates easier.

## Included files

- `.github/workflows/deploy-al-folio.yml`: GitHub Pages deployment workflow.
- `al-folio-overlay/_config.yml`: site configuration.
- `al-folio-overlay/_pages/*.md`: About, Publications, Team, Teaching, and Service pages.
- `al-folio-overlay/_news/*.md`: recent news items.
- `al-folio-overlay/_bibliography/papers.bib`: publication records in BibTeX format.
- `al-folio-overlay/_data/cv.yml`: structured CV data.

## After merging

Go to **Settings → Pages → Build and deployment → Source** and select **GitHub Actions**. Then run the `Deploy al-folio academic homepage` workflow manually once, or push another commit to `main`.

## Notes

The old `index.html` and `styles.css` are intentionally kept as a fallback. Once the al-folio deployment is verified, they can be removed in a follow-up cleanup PR.
