# joshkaki00.github.io

Personal landing page, built with [Jekyll](https://jekyllrb.com/) and styled with [Tailwind CSS](https://tailwindcss.com/), compiled via the [Tailwind CLI](https://tailwindcss.com/docs/installation/tailwind-cli) into a minified, purged production stylesheet (no CDN script — the Play CDN build is [explicitly for development only](https://tailwindcss.com/docs/installation/play-cdn)).

## Structure

- `_config.yml` — site metadata and all editable landing-page content (hero text, skills, projects, social links)
- `_layouts/default.html` — base HTML layout
- `_includes/` — `head.html`, `nav.html`, `footer.html` partials
- `index.html` — the landing page sections (hero, about, skills, projects, contact)
- `assets/css/input.css` — Tailwind entry point and `@theme` customizations (brand colors, font)
- `assets/css/style.css` — **generated** compiled CSS (not committed; built by CI on every deploy)

## Editing content

Most content (name, role, summary, skills, projects, links) lives in `_config.yml` — edit the values there and the page updates automatically. No need to touch the HTML for routine updates.

## Local development

```bash
bundle install
npm install

npm run watch:css      # rebuilds assets/css/style.css on change
bundle exec jekyll serve --livereload   # in a second terminal
```

Then open `http://localhost:4000`.

To do a one-off production-style build locally:

```bash
npm run build:css
bundle exec jekyll build
```

## Deployment

This repo is a GitHub Pages user site (`Joshkaki00.github.io`), deployed via the [`.github/workflows/pages.yml`](.github/workflows/pages.yml) GitHub Actions workflow: it installs Ruby + Node, runs `npm run build:css` to compile Tailwind, builds the Jekyll site, and publishes it with `actions/deploy-pages`.

**One-time setup required:** in the repo's Settings → Pages, set **Source** to **GitHub Actions** (instead of "Deploy from a branch") so this workflow — rather than GitHub's default Jekyll builder — controls the build.
