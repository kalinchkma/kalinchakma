# Kalin Chakma · Portfolio

My personal portfolio: projects, experience, publications and CV.

**Live site:** https://kalinchkma.github.io/kalinchakma/

Built with [Jekyll](https://jekyllrb.com/) on the [al-folio](https://github.com/alshedivat/al-folio) starter (v1.x), with a custom design. Deployed to GitHub Pages by GitHub Actions (`.github/workflows/jekyll.yml`).

---

## Contents

- [How updating works](#how-updating-works)
- [Where everything lives](#where-everything-lives)
- [Updating your content](#updating-your-content)
  - [About / home page](#about--home-page)
  - [Profile photo](#profile-photo)
  - [News](#news)
  - [Projects](#projects)
  - [CV](#cv)
  - [Publications](#publications)
  - [Social links](#social-links)
  - [GitHub repositories page](#github-repositories-page)
  - [Blog posts](#blog-posts)
  - [Navigation menu](#navigation-menu)
- [Changing the design](#changing-the-design)
- [Previewing locally](#previewing-locally)
- [First-time GitHub Pages setup](#first-time-github-pages-setup)
- [Updating the al-folio theme](#updating-the-al-folio-theme)
- [Troubleshooting](#troubleshooting)

---

## How updating works

1. Edit a file, either on github.com (open the file and click the ✏️ pencil) or locally in your editor.
2. Commit and push to `main`.
3. GitHub Actions rebuilds the site (**Actions → Deploy Jekyll site to Pages**). It's live 2–4 minutes later.

That's all. Pull requests to `main` are built but not deployed, so you can check a change compiles before merging it.

---

## Where everything lives

| What you want to change               | File / folder                                        |
| ------------------------------------- | ---------------------------------------------------- |
| Name, site description, URL, features | `_config.yml`                                        |
| Home page bio, tagline, tech chips    | `_pages/about.md`                                    |
| News items on the home page           | `_news/*.md`                                         |
| Projects                              | `_projects/*.md`                                     |
| CV page content                       | `_data/cv.yml`                                       |
| Downloadable CV PDF                   | `assets/pdf/kalin_chakma_cv.pdf`                     |
| Publications                          | `_bibliography/papers.bib`                           |
| Social icons (email, GitHub, …)       | `_data/socials.yml`                                  |
| Repositories page                     | `_data/repositories.yml`                             |
| Blog posts                            | `_posts/YYYY-MM-DD-title.md`                         |
| Images                                | `assets/img/`                                        |
| Colors, fonts, design                 | `assets/css/main.scss` (the "Design tokens" section) |

---

## Updating your content

### About / home page

Edit `_pages/about.md`.

- `subtitle:` is the line under your name.
- The text below the second `---` is your bio (Markdown).
- `<p class="kc-lead">…</p>` is the large intro sentence.
- `<div class="kc-stack">…</div>` holds the tech "chips". Add or remove `<span>Tech</span>` entries.
- `more_info:` is the small status badge under the photo area.

### Profile photo

1. Add a square photo as `assets/img/prof_pic.jpg` (at least 400×400 px).
2. In `_pages/about.md`, uncomment the line:
   ```yaml
   image: prof_pic.jpg
   ```
3. `image_circular: true` makes it round; set it to `false` for rounded corners.

### News

Each file in `_news/` is one line on the home page, newest first. To add one, create `_news/2026-12-new-thing.md`:

```markdown
---
layout: post
date: 2026-12-01 10:00:00+0600
inline: true
related_posts: false
---

Shipped **something cool** at work. :rocket:
```

For a longer news item with its own page, set `inline: false` and add a `title:`.

### Projects

Each file in `_projects/` is one card on the **projects** page. To add one, copy an existing file, e.g. `_projects/1_geko.md`:

```markdown
---
layout: page
title: My New Project
description: One-line summary shown on the card.
importance: 7 # lower number = shown first
category: open source # "work" or "open source" (the groups on the projects page)
github: https://github.com/kalinchkma/my-new-project # optional: adds a GitHub icon
img: assets/img/my-project.png # optional: card thumbnail
---

Write about the project here in Markdown.
```

To add a new category, add it to `display_categories` in `_pages/projects.md`.

### CV

The CV appears in two places:

1. **The `/cv/` page** is generated from `_data/cv.yml`. Edit entries there. For example, add a job at the top of `Experience:`:
   ```yaml
   - company: New Company
     position: Senior Software Engineer
     location: Dhaka, Bangladesh
     start_date: 2027-01 # leave out end_date to show "Present"
     highlights:
       - What you did.
   ```
2. **The PDF download** (the PDF icon on the CV page and in the social icons) is `assets/pdf/kalin_chakma_cv.pdf`. To update it, replace that file with your new PDF and keep the same name.

### Publications

Add BibTeX entries to `_bibliography/papers.bib`. Useful extra fields:

| Field                  | Effect                                     |
| ---------------------- | ------------------------------------------ |
| `selected = {true}`    | Also shows the paper on the home page      |
| `abbr = {DiB}`         | Colored venue badge (colors in `_data/venues.yml`) |
| `html = {https://…}`   | "HTML" button                              |
| `pdf = {https://…}`    | "PDF" button                               |
| `code = {https://…}`   | "Code" button                              |
| `abstract = {…}`       | "Abstract" toggle                          |
| `bibtex_show = {true}` | "Bib" toggle                               |

Your name is highlighted automatically (`scholar.last_name` / `first_name` in `_config.yml`).

Tip: on Google Scholar or the journal page, click **Cite → BibTeX** and paste the result into `papers.bib`.

### Social links

Edit `_data/socials.yml`. Uncomment and fill in the lines you want, e.g.:

```yaml
linkedin_username: kalin-chakma
x_username: kalinchkma
```

All supported networks: https://github.com/george-gca/jekyll-socials

### GitHub repositories page

Edit `_data/repositories.yml` and list the repos to show as `owner/repo-name`.

### Blog posts

The blog is hidden until you write something.

1. Create `_posts/2026-12-01-my-first-post.md`:

   ```markdown
   ---
   layout: post
   title: My first post
   date: 2026-12-01 10:00:00+0600
   description: A short summary.
   tags: [golang, backend]
   categories: [engineering]
   ---

   Write your post in Markdown here.
   ```

2. In `_pages/blog.md`, change `nav: false` to `nav: true` to show **blog** in the menu.
3. In `_pages/about.md`, set `latest_posts: enabled: true` to list recent posts on the home page.

### Navigation menu

Each page in `_pages/` with `nav: true` appears in the top menu, sorted by `nav_order`. Set `nav: false` to hide a page.

---

## Changing the design

All custom styling is in **`assets/css/main.scss`**, below the "Kalin Chakma: custom design layer" comment.

- **Colors:** change the variables at the top of that section. `:root { … }` is light mode, `html[data-theme="dark"] { … }` is dark mode. The main ones are `--kc-accent` (teal) and `--kc-accent-2` (amber).
- **Fonts:** `--kc-font-body`, `--kc-font-head` and `--kc-font-mono`. When you switch to a different Google Font, also update the `google_fonts` URL in `_config.yml` (search for `google_fonts`).
- **Site icon (favicon):** `icon:` in `_config.yml`, either an emoji or an image file in `assets/img/`.
- **Features:** toggles like dark mode, search and the scroll progress bar are the `enable_*` options near the bottom of `_config.yml`.

`assets/css/main.scss` overrides the al-folio theme's own file. After a theme update, run `bundle exec al-folio upgrade overrides audit`. It tells you whether the theme's version changed and needs merging (see [Updating the al-folio theme](#updating-the-al-folio-theme)).

---

## Previewing locally

You need [Docker Desktop](https://www.docker.com/products/docker-desktop/):

```bash
docker compose up
```

Then open **http://localhost:8080/kalinchakma/**. Most changes reload automatically. Changes to `_config.yml` restart the server, which takes a few seconds.

Stop it with `Ctrl+C`, or run `docker compose down`.

---

## First-time GitHub Pages setup

You only need to do this once.

1. **The repo must be public** (free accounts can't publish GitHub Pages from a private repo): **Settings → General → Danger Zone → Change visibility → Public**.
2. **Settings → Pages → Build and deployment → Source: GitHub Actions.**
3. Push to `main`, or open **Actions → Deploy Jekyll site to Pages → Run workflow**. Wait for both jobs (`build`, `deploy`) to show a green ✓.
4. Your site is live at **https://kalinchkma.github.io/kalinchakma/**. The deploy job also shows the link.

### Want the shorter URL `https://kalinchkma.github.io/`?

1. Rename the repo to **`kalinchkma.github.io`** (Settings → General → Repository name).
2. In `_config.yml`, set `baseurl:` to empty (keep the line itself):
   ```yaml
   url: https://kalinchkma.github.io
   baseurl:
   ```
3. Update the local git remote:
   ```bash
   git remote set-url origin git@github.com:kalinchkma/kalinchkma.github.io.git
   ```
4. Push. The workflow picks up the new path automatically. Local preview is then at http://localhost:8080/.

---

## Updating the al-folio theme

In al-folio v1.x, the layouts and features come from versioned Ruby gems (`al_folio_core`, `al_folio_cv`, …), pinned in the `Gemfile`. You don't need to merge anything from the upstream repo. Update occasionally, when you want new features or fixes:

```bash
# inside the Docker container (or with Ruby 3.2+ installed locally)
docker compose run --rm jekyll bash
bundle update --all
bundle exec al-folio upgrade audit             # what needs changing
bundle exec al-folio upgrade apply --safe      # apply automatic safe fixes
bundle exec al-folio upgrade report            # writes al-folio-upgrade-report.md
bundle exec al-folio upgrade overrides audit   # checks assets/css/main.scss against the new theme
exit
```

Preview with `docker compose up`. If everything looks right, commit `Gemfile.lock` (and `.al-folio-overrides.yml` if it changed) and push.

The **Upgrade contract checks** workflow also runs the audit on every push and attaches a report to the run.

More detail: [`docs/INSTALL.md`](docs/INSTALL.md), [`docs/CUSTOMIZE.md`](docs/CUSTOMIZE.md), [`docs/FAQ.md`](docs/FAQ.md).

---

## Troubleshooting

| Problem                                         | Fix                                                                                                                       |
| ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Site has no styling / links are broken          | `url` and `baseurl` in `_config.yml` don't match the repo name. See [First-time setup](#first-time-github-pages-setup). |
| Pushed but nothing changed                      | Check **Actions → Deploy Jekyll site to Pages** for a red ✗ and open the log. Then hard-refresh the browser (`Cmd+Shift+R`). Pushes that only change `README.md` or `docs/` don't trigger a deploy. |
| `deploy` job fails / "Get Pages site failed"    | Settings → Pages → Source must be **GitHub Actions**.                                                                     |
| A feature doesn't show and there's no error     | It needs both its gem in `Gemfile` and its entry under `plugins:` in `_config.yml`, and its `enable_*` flag on.           |

---

## License

Site content © Kalin Chakma. The underlying al-folio template is [MIT-licensed](LICENSE).
