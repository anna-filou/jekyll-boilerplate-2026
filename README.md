# Jekyll Boilerplate 2026 (Pages CMS)

A minimal Jekyll site with content in YAML data files and optional editing via [Pages CMS](https://pagescms.org/). Use it as a starting point for any static site.

## Quick start

```bash
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000`. The root `/` is the homepage; `/blog`, `/terms`, and `/privacy` are the main pages.

---

## Project structure

```
├── _config.yml          # Jekyll config (url, etc.)
├── _data/               # All editable content (YAML)
│   ├── contact.yml
│   ├── footer.yml
│   ├── nav.yml
│   └── seo.yml
├── _includes/
│   ├── footer.html      # Footer (uses footer.yml)
│   ├── head.html        # Meta, SEO, CSS
│   └── nav.html         # Site title + nav links
├── _layouts/
│   ├── default.html     # Wrapper: head, nav, main, footer
│   ├── index.liquid     # Homepage (data dump)
│   ├── blog.liquid      # Blog index
│   └── article.liquid   # Terms, privacy, etc.
├── _posts/              # Blog posts
├── index.html           # Homepage
├── blog.md              # Blog index page
├── terms.md             # Terms page
├── privacy.md           # Privacy page
├── 404.html
├── assets/
│   ├── css/style.css
│   └── img/meta/        # Add favicon.svg, og.jpg here
└── .pages.yml           # Pages CMS schema (edits _data/*.yml)
```

---

## Content

All editable text lives in `_data/*.yml`. Layouts and includes use `site.data` to pull in that content (e.g. `site.data.seo.title`, `site.data.contact.company`). Keep HTML in `_layouts/` and `_includes/`; pages in the root and `_posts/` use front matter (`layout`, `title`) and, where needed, minimal content that the layout renders.

Blog posts go in `_posts/` with standard Jekyll front matter. The sample post uses `permalink: /blog/draft-post/` so posts live under `/blog/`. Terms and privacy are plain markdown pages (`terms.md`, `privacy.md`); edit their content directly in those files.

## Pages CMS

`.pages.yml` defines how Pages CMS edits the `_data` files. When you edit content in the CMS, it writes back to `_data/contact.yml`, `_data/seo.yml`, etc.

---

## Meta assets

Place these under `assets/img/meta/`:

- **favicon.svg** — Browser tab icon.
- **og.jpg** — Social sharing image (e.g. 1200×630). Set `seo.image` in `_data/seo.yml` to `/assets/img/meta/og.jpg` when you add it.

---

## License

Use and adapt as you like.
