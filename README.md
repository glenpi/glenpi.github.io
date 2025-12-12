# glenpi.github.io

Personal site powered by [Hugo](https://gohugo.io/) and a small custom theme that lives in `themes/glenpi`.

## Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) `v0.152+`

## Local development

```bash
hugo server --buildDrafts
```

The command serves the site at http://localhost:1313, watches for content/theme changes, and rebuilds drafts for quick iteration.

## Production build

```bash
hugo
```

The static output lands in the `public` directory and is ready to be pushed to GitHub Pages.
