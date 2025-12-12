# Creating New Posts

The Hugo CLI keeps content creation simple. This repo already includes the default archetype in `archetypes/default.md`, so every new post starts with sensible front matter.

## 1. Generate the post

From the repo root:

```bash
hugo new posts/my-new-post.md
```

Hugo will place the file under `content/posts/` with the boilerplate front matter. The name determines the slug (`my-new-post` in the URL). Prefer lowercase words separated by dashes.

### Optional: bundle format

If you want to keep images or other assets next to the article, create a bundle:

```bash
hugo new --kind default posts/my-new-post/index.md
```

This yields a folder `content/posts/my-new-post/` where you can drop images and reference them with `{{< figure src="image.jpg" >}}` etc.

## 2. Update the front matter

Open the generated Markdown file and adjust the block at the top:

```toml
+++
title = "Meaningful Title"
date = 2024-01-01T09:00:00Z
description = "One-sentence summary that shows in cards."
tags = ["topic", "another"]
draft = false
+++
```

- Flip `draft` to `false` when ready to publish.
- `description` feeds the cards on the homepage/posts listing.
- Add `tags` to group related articles; the template renders them on the post detail pages.

## 3. Write the content

Below the front matter, write in Markdown. Feel free to use Hugo shortcodes if you need richer elements (e.g., `{{< highlight go >}}` for code blocks). When working inside bundles, reference local assets with relative paths (e.g., `![Diagram](diagram.png)`).

## 4. Preview locally

```bash
hugo server --buildDrafts
```

This serves the site at <http://localhost:1313>, rebuilds on file changes, and includes draft posts (great while iterating). Once the post is ready, set `draft = false` and rebuild to ensure it appears in the production build.

## 5. Commit and push

Add the new file(s) to Git, commit, and push `main`. The GitHub Action in `.github/workflows/deploy.yml` will build the site and deploy updated content to GitHub Pages.
