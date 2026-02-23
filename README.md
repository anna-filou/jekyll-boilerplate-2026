# Jekyll Boilerplate 2026 (Pages CMS)

A minimal Jekyll site with content in YAML data files and optional editing via [Pages CMS](https://pagescms.org/). Use it as a starting point for any static site.

## Quick start

```bash
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000`. The root `/` is the homepage; `/blog`, `/works`, `/terms`, and `/privacy` are the main pages. If you change `_config.yml` (e.g. collections), restart the server for changes to apply.

---

## Project structure

```
├── _config.yml          # Jekyll config (collections, etc.)
├── _data/               # Editable content (YAML), editable via Pages CMS
│   ├── contact.yml
│   ├── footer.yml
│   ├── nav.yml
│   └── seo.yml          # url, title, description, image (OG/twitter)
├── _includes/
│   ├── footer.html      # Footer (uses footer.yml)
│   ├── head.html        # Meta, SEO, CSS, OG/twitter image
│   └── nav.html         # Site title + nav links (from nav.yml)
├── _layouts/
│   ├── default.html     # Wrapper: head, nav, main, footer
│   ├── index.liquid     # Homepage (data dump + blog/works lists)
│   ├── blog.liquid      # Blog index
│   ├── works.liquid     # Works index
│   └── article.liquid   # Terms, privacy, work detail, etc.
├── _posts/              # Blog posts
├── _works/              # Works collection (output: true, permalink: /:name/)
├── index.html           # Homepage
├── blog.md              # Blog index → /blog/
├── works.md             # Works index → /works/
├── terms.md             # Terms (markdown body)
├── privacy.md           # Privacy (markdown body)
├── 404.html
├── assets/
│   ├── css/style.css
│   └── img/meta/        # favicon.svg, og.jpg
└── .pages.yml           # Pages CMS schema (edits _data/*.yml)
```

---

## Content

- **Data:** Editable text lives in `_data/*.yml`. Layouts and includes use `site.data` (e.g. `site.data.seo.title`, `site.data.contact.company`). The site URL and OG image path are in `seo.yml`; nav links come from `nav.yml` and are rendered in `nav.html`. Keep HTML in `_layouts/` and `_includes/`; pages use front matter and, where needed, markdown in the body.
- **Blog:** Posts go in `_posts/` with standard Jekyll front matter. The sample post uses `permalink: /blog/draft-post/` so posts live under `/blog/`. The blog index is at `/blog/`.
- **Works:** The `works` collection lives in `_works/`. Each document has front matter (e.g. `title`, `description`, `hero_image`) and markdown body; they are output with `permalink: /:name/`. The works index at `/works/` lists all works (see `works.md` and `_layouts/works.liquid`).
- **Terms & privacy:** Plain markdown pages (`terms.md`, `privacy.md`); edit their content in those files. Privacy can still use `site.data.contact` for company/address.

## Pages CMS

`.pages.yml` defines how Pages CMS edits the `_data` files. When you edit content in the CMS, it writes back to `_data/contact.yml`, `_data/seo.yml`, etc.

---

## Meta assets

Place these under `assets/img/meta/`:

- **favicon.svg** — Browser tab icon.
- **og.jpg** — Social sharing image (e.g. 1200×630). Set `image` in `_data/seo.yml` to `/assets/img/meta/og.jpg`; `url` in the same file is used to build absolute OG/twitter image URLs.

---

## License

Use and adapt as you like.
