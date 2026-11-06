# CLAUDE.md

This is **Kalin Chakma's personal portfolio**, a site created from the al-folio v1.x starter. It is not the al-folio starter repo itself.

- Content workflow and file map: see `README.md`.
- Repo is `kalinchkma.github.io` (user site): `baseurl` is empty, site at https://kalinchkma.github.io/. Local preview: `docker compose up` → http://localhost:8080/
- `README.md` is the owner's GitHub profile-style README; the site maintenance guide is `README.site.md`. Both are excluded from the build.
- Custom design lives in the local override `assets/css/main.scss` (theme partials first, then the custom layer). Local overrides are allowed in a user site; after gem bumps, run `bundle exec al-folio upgrade overrides audit`.
- `AGENTS.md` describes the upstream starter. Its "stop sign" for `_layouts/`, `_includes/` and `_sass/` applies to contributions to al-folio, not to this site.
- Deploy: `.github/workflows/jekyll.yml` builds on push to `main` and deploys with the official GitHub Pages actions (Pages source = "GitHub Actions"; no `gh-pages` branch). Pull requests are build-only. url/baseurl come from `_config.yml` only.
