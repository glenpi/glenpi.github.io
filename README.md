# glenpi.github.io

Personal site powered by [Hugo](https://gohugo.io/) and the minimalist [nostyleplease theme](https://github.com/hanwenguo/hugo-theme-nostyleplease).

## Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) `v0.152+`

## Local development

```bash
hugo server --buildDrafts
```

The command serves the site at http://localhost:1313, watches for content/theme changes, and includes drafts so you can iterate quickly. Menu entries live in `data/menu.toml`; global theme tweaks are controlled through `hugo.toml` under `[params.theme_config]`.

## Production build

```bash
hugo --gc --minify
```

The static output lands in the `public` directory and is deployed automatically to GitHub Pages by `.github/workflows/deploy.yml`.
