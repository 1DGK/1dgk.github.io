Project: 1dgk.github.io — Jekyll personal site

This repository is a Jekyll-based static site (user page) built from Markdown.
Instructions here are specific and actionable so an AI coding agent can be immediately productive.

- Big picture:
  - Source content lives in Markdown: pages at the repo root (e.g. `index.md`, `projects.md`) and posts in `_posts/`.
  - Drafts are in `_drafts/` and are not published unless explicitly enabled.
  - Jekyll generates the site into `_site/` (do not edit this folder — it is generated output).
  - Templates and site layout are under `_layouts/` and `_includes/` (standard Jekyll conventions).

- Key files and examples:
  - `_config.yml` — global site config and theme (`minima`) and plugins (`jekyll-feed`). Example: baseurl is empty.
  - `Gemfile` — use Bundler to install Jekyll + gems locally.
  - Posts: `_posts/2026-01-07-java-module-4.md` — each post uses YAML front matter. Minimal required fields seen in repo:
    ```yaml
    ---
    layout: post
    title: Java Module 4 - Conditionals and Loops
    ---
    ```
  - Avoid editing `_site/` and `.jekyll-cache/` — they are generated/temporary.

- Developer workflows (commands you can run locally):
  - Install dependencies: `bundle install`
  - Serve locally with live reload: `bundle exec jekyll serve --livereload`
  - Build static site: `bundle exec jekyll build` (output -> `_site/`)
  - Notes: `_config.yml` is not reloaded automatically by `jekyll serve` — restart server after config changes.

- Content and authoring conventions to follow:
  - New posts: create a Markdown file in `_posts/` named `YYYY-MM-DD-title.md`. The date in the filename drives the post date/permalink.
  - Front matter: include at minimum `layout: post` and `title:`. See `_posts/2026-01-07-java-module-4.md` for example.
  - Drafts: place unpublished pieces in `_drafts/` using the same front matter pattern.
  - Internal links: site uses root-relative links (e.g. `/projects`) because `baseurl: ""` in `_config.yml`.

- Patterns and project-specific notes for code changes:
  - Theme: site uses the `minima` theme; prefer changes via `_layouts/` or `_includes/` rather than hacking the theme gem.
  - Keep content Markdown-first; the repository contains many hand-written posts — preserve tone and front-matter style.
  - Static assets and special content: `latex/` contains additional artifacts — treat as static resources.

- CI / deployment hints:
  - This repo is named `1dgk.github.io` (user page). Publishing is typically handled by GitHub Pages from the `main` branch — pushing to `main` will update the public site.

- What to avoid / watch for:
  - Do not commit generated files from `_site/` or the `.jekyll-cache/` directory.
  - `_config.yml` changes require a server restart to take effect locally.

- When you need more context, inspect these files:
  - [/_config.yml](_config.yml)
  - [/_posts/2026-01-07-java-module-4.md](_posts/2026-01-07-java-module-4.md) (example post)
  - [/Gemfile](Gemfile)

If anything here is unclear or you want additional examples (e.g., common layout edits, example includes, or a local Docker dev environment), tell me which area to expand.
