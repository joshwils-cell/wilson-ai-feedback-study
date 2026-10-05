# wilson-ai-feedback-study

> R package supporting Joshua Wilson, Ph.D.'s dissertation, "From AI Feedback to Independent Writing: Evaluating a Revision and Goal-Setting Routine in Middle School", provisioned via [dissertation.ai](https://dissertation-ai.dataimago.ai).

**📖 Website:** [joshwils-cell.github.io/wilson-ai-feedback-study](https://joshwils-cell.github.io/wilson-ai-feedback-study/) — the thesis as an HTML book, the latest thesis PDF, and the R package reference rendered from the roxygen docs. Published by `quarto-publish.yml` on every push (a maintainer or the provisioning flow must enable GitHub Pages, build type "GitHub Actions", once).

This package is the **R-package half** of a two-repo dissertation environment. The NextJS app half lives at [`github.com/joshwils-cell/joshwils-cell-dissertation`](https://github.com/joshwils-cell/joshwils-cell-dissertation) and includes this package as a Git submodule at `packages/r-packages/wilson-ai-feedback-study/`.

## What's in this repo

| Path | Purpose |
|---|---|
| `R/` | Your methodological R code |
| `tests/testthat/` | Unit tests |
| `ui/www/` | The Quarto book that becomes your thesis PDF |
| `ui/www/chapters/` | Per-chapter `.qmd` sources |
| `ui/www/thesis.cls` | LaTeX thesis class (see `ui/www/THESIS-CLS-README.md` for the 3-mode strategy) |
| `ui/www/references.bib` | BibTeX bibliography |
| `.github/workflows/build-thesis.yml` | Renders thesis PDF on every push that touches `ui/www/` or `R/` |
| `.github/workflows/quarto-publish.yml` | Publishes the HTML book + PDF + package reference to GitHub Pages |
| `.github/workflows/R-CMD-check.yml` | R package CI |
| `DESCRIPTION` | R package metadata |

## Quick start

```sh
git clone https://github.com/joshwils-cell/wilson-ai-feedback-study.git
cd wilson-ai-feedback-study

# Edit chapter content in ui/www/chapters/*.qmd
# (or open this repo in your AI-enabled editor)

# Local thesis PDF preview
cd ui/www && quarto preview

# Or push to main + check the CI-built PDF in docs/thesis.pdf
```

## Editing your dissertation

| What you want to change | Where |
|---|---|
| Thesis chapter content | `ui/www/chapters/*.qmd` |
| Bibliography | `ui/www/references.bib` |
| Thesis formatting (margins, title page, etc.) | `ui/www/thesis.cls` (see `ui/www/THESIS-CLS-README.md`) |
| Quarto book config (chapters list, PDF format, fonts) | `ui/www/_quarto.yml` |
| Methodology R code | `R/*.R` |

## The two-repo relationship

This R package + the dissertation app at `github.com/joshwils-cell/joshwils-cell-dissertation` are designed to be edited together. Most users clone the app repo with `--recursive` to get both at once. Changes to thesis content + R code go in this repo; changes to the spec + landing page + app-level configuration go in the app repo.

## Framework links

- [dissertation.ai](https://dissertation-ai.dataimago.ai) — the hub that provisioned this repo
- [dataimago](https://github.com/dataimago/dataimago) — the framework this package is built on
- [dissertation-rpkg-template](https://github.com/dataimago/dissertation-rpkg-template) — the template this repo was made from

## License

MIT
