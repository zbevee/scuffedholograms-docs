# ScuffedHolograms Documentation

This repository holds the source for the ScuffedHolograms documentation site. It contains **only documentation**, no plugin source code.

The site is built with [MkDocs](https://www.mkdocs.org/) and the [Material theme](https://squidfunk.github.io/mkdocs-material/).

## Editing

All pages live in `docs/` as Markdown. The site navigation is defined in `mkdocs.yml`.

## Previewing locally

```bash
pip install -r requirements.txt
mkdocs serve
```

Then open <http://127.0.0.1:8000>.

## Publishing

Pushing to the `main` branch triggers the GitHub Action in `.github/workflows/deploy.yml`, which builds the site and publishes it to GitHub Pages (the `gh-pages` branch). Enable Pages in the repository settings (Source: `gh-pages` branch) once after the first deploy.
