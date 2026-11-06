# CLAUDE.md

This is **Kalin Chakma's personal portfolio**, a site created from the al-folio v1.x starter. It is not the al-folio starter repo itself.

- Content workflow and file map: see `README.md`.
- Site baseurl is `/kalinchakma` (project page at https://kalinchkma.github.io/kalinchakma/). Local preview: `docker compose up` → http://localhost:8080/kalinchakma/
- Custom design lives in the local override `assets/css/main.scss` (theme partials first, then the custom layer). Local overrides are allowed in a user site; after gem bumps, run `bundle exec al-folio upgrade overrides audit`.
- `AGENTS.md` describes the upstream starter. Its "stop sign" for `_layouts/`, `_includes/` and `_sass/` applies to contributions to al-folio, not to this site.
- Deploy: `.github/workflows/deploy.yml` builds on push to `main` and publishes to `gh-pages`.
