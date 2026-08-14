# suraj1102.github.io

Personal site, built with [Quarto](https://quarto.org) and deployed to GitHub
Pages by the workflow in `.github/workflows/publish.yml` on every push to `main`.

## Local development

```bash
quarto preview
```

Renders to `_site/` (gitignored). `quarto render` does a one-off build.

## Layout

```
index.qmd                    home: about band, experience list, project grid
projects/<slug>/index.qmd    one folder per project, images alongside
experience/<slug>/index.qmd  one folder per role
theme/light.scss             light palette
theme/dark.scss              dark palette
theme/shared.scss            shared rules (cards, typography, link rows)
_listings/card.ejs.md        custom project-card template
_partials/back-link.html     "back to home" link on detail pages
assets/                      favicons, avatar, PDFs, original source images
```

## Adding a project

1. `mkdir projects/my-project` and add an `index.qmd`.
2. Front matter drives the card on the homepage:

```yaml
---
title: "My Project"
subtitle: "CS1234: Course Name"       # shown under the title
description: "One line. This is the card blurb."
categories: [Course]                  # or [Research] — becomes the badge
order: 8                              # controls position in the grid
image: thumb.webp                     # optional; card degrades to text if absent
image-alt: "Description of the image"
author:
  - name: Suraj Dayma
    url: /
    affiliation: Plaksha University
---
```

3. Optional link row:

```markdown
::: {.link-row}
[<i class="bi bi-github"></i> Code](https://github.com/...)
[<i class="bi bi-file-earmark-pdf"></i> Report](/assets/files/report.pdf)
:::
```

Icons are [Bootstrap Icons](https://icons.getbootstrap.com), bundled by Quarto —
no CDN needed.

## Images

Card thumbnails are ~800px WebP; full-size images ~1200px WebP:

```bash
magick source.png -resize '800>' -strip -quality 80 projects/my-project/thumb.webp
```

Originals live in `assets/img/projects/` and are excluded from the published
site via the `resources` block in `_quarto.yml`.
