# carlosaaguila.github.io

Personal academic website for **Carlos Aguila** — PhD candidate in Bioengineering at the University of Pennsylvania (expected Fall 2026), working at the intersection of computational neuroscience, machine learning, and clinical epileptology.

Live site: [carlosaaguila.github.io](https://carlosaaguila.github.io)

---

## Stack

| Layer      | Technology                                                    |
| ---------- | ------------------------------------------------------------- |
| Framework  | [Jekyll](https://jekyllrb.com/) (static site generator)       |
| Theme      | [al-folio](https://github.com/alshedivat/al-folio) v0.16.3    |
| Hosting    | GitHub Pages (auto-deploys on push to `main`)                 |
| Templating | Liquid (`.liquid` files)                                      |
| Styling    | SCSS (`_sass/`) compiled by Jekyll                            |
| Local dev  | Docker (`docker compose up` → `localhost:8080`)               |
| Formatting | Prettier + `@shopify/prettier-plugin-liquid` (enforced in CI) |

---

## Repository structure

```
.
├── _pages/              # Site pages (each = one route)
│   ├── about.md         # Homepage / About (/)
│   ├── cv.md            # CV page with embedded PDF viewer
│   ├── publications.md  # Publications (powered by _bibliography/)
│   ├── research.md      # Research overview
│   ├── teaching.md      # Teaching
│   ├── projects.md      # Projects
│   ├── news.md          # News feed
│   └── books.md         # Book shelf
│
├── _layouts/            # Page layout templates
│   ├── about.liquid     # Homepage layout (profile + carousel)
│   ├── cv.liquid        # CV layout
│   ├── default.liquid   # Base layout
│   └── ...
│
├── _includes/           # Reusable partials (header, footer, figure, etc.)
│
├── _sass/               # SCSS stylesheets
│   ├── _layout.scss     # Main layout styles (incl. about-carousel)
│   ├── _themes.scss     # Light/dark theme variables
│   └── ...
│
├── _bibliography/
│   └── papers.bib       # BibTeX file — source of truth for publications
│
├── _data/               # Structured data (YAML)
│   ├── cv.yml           # CV entries rendered on /cv
│   ├── socials.yml      # Social media links
│   ├── coauthors.yml    # Co-author metadata for publications
│   └── repositories.yml # GitHub repos shown on /repositories
│
├── _news/               # News items (one .md file per item)
├── _posts/              # Blog posts
├── _projects/           # Project cards
├── _teachings/          # Teaching entries
│
├── assets/
│   ├── img/
│   │   ├── prof_pic.jpg          # Profile photo
│   │   └── about-carousel/       # Photos shown in About page carousel
│   │       ├── pic1.jpg – pic7.jpg
│   ├── pdf/                      # CV and résumé PDFs
│   └── js/                       # Custom JavaScript
│
├── _config.yml          # Jekyll site config (name, URL, plugins, theme vars)
├── Gemfile              # Ruby dependencies
├── package.json         # Node dependencies (Prettier)
└── .github/workflows/   # CI/CD pipelines (see below)
```

---

## Key pages

### About (`_pages/about.md`)

Homepage. Controls:

- Profile photo (`profile.image`)
- Subtitle and contact info (`profile.more_info`)
- Bio text (Markdown body)
- Photo carousel (`profile_carousel` list of image paths)
- News feed toggle (`news: true/false`)
- Social icons (`social: true/false`)

Carousel images live in `assets/img/about-carousel/`. Add a new image path to the `profile_carousel` list in the front matter to include it. Images should be portrait orientation (900×1200) for consistent display — use Pillow to letterbox landscape photos.

### CV (`_pages/cv.md`)

Embeds PDF directly. Two files:

- `assets/pdf/CV_Aguila.pdf` — full academic CV
- `assets/pdf/Resume_Aguila.pdf` — industry résumé

Toggle between them via a button rendered in the page.

### Publications (`_pages/publications.md`)

Powered by [jekyll-scholar](https://github.com/inukshuk/jekyll-scholar). Edit `_bibliography/papers.bib` to add/update publications. Co-author links configured in `_data/coauthors.yml`.

---

## CI/CD

| Workflow               | Trigger        | What it does                                                                          |
| ---------------------- | -------------- | ------------------------------------------------------------------------------------- |
| `deploy.yml`           | push to `main` | Builds Jekyll, deploys to GitHub Pages                                                |
| `prettier.yml`         | push / PR      | Checks formatting — fails if any `.liquid`, `.scss`, `.md` file is not Prettier-clean |
| `broken-links.yml`     | push           | Checks for dead links in built site                                                   |
| `update-citations.yml` | schedule       | Pulls citation counts from Google Scholar                                             |
| `render-cv.yml`        | push           | Re-renders CV PDF if source changes                                                   |

**If Prettier CI fails:** run `npx prettier . --write` locally, commit, and push.

---

## Local development

```bash
docker compose up
# → http://localhost:8080
```

Requires Docker Desktop running. Uses the pre-built `amirpourmand/al-folio:v0.16.3` image.

---

## Adding content

| Task                 | What to edit                                                                              |
| -------------------- | ----------------------------------------------------------------------------------------- |
| Update bio           | `_pages/about.md` (body text)                                                             |
| Add publication      | `_bibliography/papers.bib`                                                                |
| Add news item        | New `.md` file in `_news/`                                                                |
| Add carousel photo   | Copy to `assets/img/about-carousel/`, add path to `profile_carousel` in `_pages/about.md` |
| Update CV/résumé     | Replace PDFs in `assets/pdf/`                                                             |
| Update social links  | `_data/socials.yml`                                                                       |
| Change theme colors  | `_sass/_themes.scss`                                                                      |
| Update site metadata | `_config.yml` (requires server restart)                                                   |

---

## Original theme

This site is built on the [al-folio](https://github.com/alshedivat/al-folio) Jekyll theme. The original theme README is preserved at `README.alfolio.md` for reference.
