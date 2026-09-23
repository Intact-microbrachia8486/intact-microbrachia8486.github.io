# gradill22.github.io

My personal site — portfolio, notes, and CV — built with
[**Jekyll**](https://jekyllrb.com/) and the
[**al-folio**](https://github.com/alshedivat/al-folio) theme, hosted on
[GitHub Pages](https://pages.github.com/) at <https://gradill22.github.io>.

## Sections

| Page | Source | What it is |
|------|--------|------------|
| About / home | [`_pages/about.md`](_pages/about.md) | Bio + profile photo + social links |
| Projects | [`_pages/projects.md`](_pages/projects.md) + [`_projects/`](_projects/) | A card grid, one Markdown file per project |
| Notes (blog) | [`_pages/blog.md`](_pages/blog.md) + [`_posts/`](_posts/) | Short write-ups |
| CV | [`_pages/cv.md`](_pages/cv.md) + [`assets/json/resume.json`](assets/json/resume.json) | Résumé driven by a [JSON Resume](https://jsonresume.org/) file |

## Adding a project (the main thing you'll do)

Drop a new file in [`_projects/`](_projects/) — e.g. `_projects/my-thing.md` —
and it appears on the Projects grid automatically:

```markdown
---
layout: page
title: My Thing                       # card title
description: One line · with · tags   # shown under the title
img: assets/img/my-thing.png          # cover image (put the file in assets/img/)
importance: 2                         # lower number = shown earlier
category: work
redirect: https://example.com/        # OPTIONAL: makes the card link straight to a URL
---

Longer description in Markdown. (Ignored when `redirect` is set, since the
card then links out instead of opening a detail page.)
```

- **Cover image:** any raster image (PNG/JPG) in `assets/img/`. The build makes
  responsive variants automatically.
- **Tags:** put them in the `description` line (they render on the card). To get
  filterable category tabs instead, set `enable_project_categories: true` in
  [`_config.yml`](_config.yml) and give each project a `category`.
- **External link vs. detail page:** include `redirect:` to link the card to a
  URL; omit it to let the card open a full project page built from the body.

## Adding a note

Create `_posts/YYYY-MM-DD-title.md` with `layout: post` front matter (see
[the welcome post](_posts/2026-09-23-welcome.md) for a template).

## Editing the CV

Edit [`assets/json/resume.json`](assets/json/resume.json) ([JSON Resume](https://jsonresume.org/)
format — this is what `cv_format: jsonresume` in [`_pages/cv.md`](_pages/cv.md) reads).
The scaffold has `TODO` markers where real details go. To offer a downloadable
PDF, drop it in `assets/pdf/` and uncomment `cv_pdf:` in [`_pages/cv.md`](_pages/cv.md).

## Profile photo & socials

- Replace `assets/img/prof_pic.png` with your headshot (keep the same filename).
- Set your email / GitHub / LinkedIn in [`_data/socials.yml`](_data/socials.yml).

## Local preview (Docker)

No Ruby needed locally — use the bundled Docker setup:

```bash
docker compose up
```

Then open <http://localhost:8080>. (Config: [`docker-compose.yml`](docker-compose.yml).)

## Deployment

Pushing to `main` triggers [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml),
which builds the site with Jekyll and publishes `_site` to the `gh-pages`
branch. GitHub Pages serves that branch. (Pages **Source** must be set to
*Deploy from a branch → `gh-pages`*.)

---

Theme: [al-folio](https://github.com/alshedivat/al-folio) (MIT). See
[`LICENSE`](LICENSE).
