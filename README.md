# jonasviehweger.github.io

Personal website built with [Quarto](https://quarto.org), deployed to GitHub Pages via
GitHub Actions. Lives at <https://jonasviehweger.github.io>.

## Local preview

```bash
quarto preview
```

Renders the whole site and opens a live-reloading browser tab. To do a one-off build:

```bash
quarto render
```

The built site goes to `_site/` (git-ignored). Code/notebook output is cached in `_freeze/`
(committed) so the deploy doesn't need Python.

## Adding content

- **A blog post** — create `blog/posts/<slug>/index.qmd` (or `index.ipynb` for a Jupyter
  notebook). Add `title`, `date`, `description`, and `categories` to its front matter; drop an
  `image:` for the listing thumbnail. See `blog/posts/irrigation/` and
  `blog/posts/example-jupyter-post/` for templates.
- **A publication** — paste a BibTeX entry into [`references.bib`](references.bib). It appears
  automatically on the Publications page.
- **A talk** — copy `talks/2024-example-talk/` to a new folder and edit its front matter.
- **A project** — add an entry to [`projects/projects.yml`](projects/projects.yml).

## Notebooks

Rendering `.ipynb` posts locally needs Jupyter:

```bash
pip install jupyter matplotlib numpy
```

## Deployment

Pushing to `main` triggers `.github/workflows/publish.yml`, which renders the site and
publishes it to GitHub Pages. **One-time setup:** in the repo's
*Settings → Pages*, set **Source = GitHub Actions**.
