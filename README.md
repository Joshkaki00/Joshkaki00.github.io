# joshkaki00.github.io

Personal landing page, built with [Jekyll](https://jekyllrb.com/) and styled with [Tailwind CSS](https://tailwindcss.com/) (via CDN, so no separate CSS build step is required — GitHub Pages' default Jekyll build handles everything).

## Structure

- `_config.yml` — site metadata and all editable landing-page content (hero text, skills, projects, social links)
- `_layouts/default.html` — base HTML layout
- `_includes/` — `head.html`, `nav.html`, `footer.html` partials
- `index.html` — the landing page sections (hero, about, skills, projects, contact)

## Editing content

Most content (name, role, summary, skills, projects, links) lives in `_config.yml` — edit the values there and the page updates automatically. No need to touch the HTML for routine updates.

## Local development

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000`.

## Deployment

This repo is a GitHub Pages user site (`Joshkaki00.github.io`). Pushing to `main` triggers GitHub's default Jekyll build — no custom Actions workflow is needed since only whitelisted Jekyll plugins (`jekyll-seo-tag`, `jekyll-sitemap`) and the Tailwind CDN script are used.
