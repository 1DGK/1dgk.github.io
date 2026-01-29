# Dust Diamond — A Jekyll Personal Site

A clean, minimal Jekyll site for sharing computer science learning notes, projects, and certifications. Built with the [Chirpy theme](https://github.com/cotes2020/jekyll-theme-chirpy) and optimized for readability.

**Live at:** [1dgk.github.io](https://1dgk.github.io)

## Quick Start

### Prerequisites
- Ruby 3.0 or higher
- Bundler

### Setup

Clone the repository and install dependencies:

```bash
git clone https://github.com/1dgk/1dgk.github.io.git
cd 1dgk.github.io
bundle install
```

### Local Development

Serve the site locally with live reload:

```bash
bundle exec jekyll serve --livereload
```

Visit `http://localhost:4000` in your browser.

Build the static site (output to `_site/`):

```bash
bundle exec jekyll build
```

## Project Structure

```
.
├── _config.yml           # Site configuration
├── _posts/               # Blog posts (organized by year)
├── _tabs/                # Navigation pages (About, Projects, Resources, etc.)
├── _includes/            # Reusable HTML components
├── _layouts/             # Page templates
├── assets/               # Images and static files
├── index.html            # Homepage
└── Gemfile               # Ruby dependencies
```

## Writing Content

### Blog Posts

Create a new post in `_posts/YYYY/` with the naming convention:

```markdown
---
layout: post
title: Your Post Title
---

Your content here...
```

Jekyll automatically generates URLs based on the filename date. For example:
- `_posts/2026/01-29-my-post.md` → `/2026/01/29/my-post/`

### Navigation Pages (Tabs)

Tab pages appear in the sidebar. Create in `_tabs/`:

```markdown
---
layout: page
title: Page Title
icon: fas fa-icon-name
order: 5
permalink: /page-title/
---

Your content...
```

**Fields:**
- `order`: Controls sidebar position (lower numbers appear first)
- `icon`: Font Awesome icon class
- `permalink`: Custom URL path

### Drafts

Keep unpublished work in `_drafts/`:

```markdown
---
layout: post
title: Draft Post
---
```

Drafts don't appear on the live site. To test locally:

```bash
bundle exec jekyll serve --drafts
```

## Customization

### Site Metadata

Edit `_config.yml`:

```yaml
title: Dust Diamond                           # Site title
description: Learning Computer Science...    # Meta description
url: https://1dgk.github.io                  # Site URL
github_username: 1dgk                        # GitHub profile link
avatar: /assets/img/avatar.png               # Profile image path
timezone: America/New_York                   # Your timezone
```

### Navigation Visibility

Hide specific pages from the sidebar by editing [`_includes/head.html`](_includes/head.html):

```html
<style>
  #sidebar .nav-link[href="/page-url/"] {
    display: none !important;
  }
</style>
```

This hides the page from navigation while keeping it accessible at its URL.

### Theme & Styling

The site uses the Chirpy theme. To customize:

1. **Colors & fonts:** Override in `_includes/head.html` with custom `<style>` blocks
2. **Layouts:** Copy theme files to `_layouts/` to override
3. **Includes:** Copy theme files to `_includes/` to customize components

### Plugins

Currently enabled in `_config.yml`:
- `jekyll-feed` — Generates RSS feed
- `jekyll-seo-tag` — SEO meta tags
- `jekyll-sitemap` — Generates sitemap.xml
- `jekyll-paginate` — Post pagination (10 per page)
- `jekyll-archives` — Archive pages by category/tag

## Publishing

The site deploys automatically via GitHub Pages when you push to the `main` branch.

1. Push your changes:
   ```bash
   git add .
   git commit -m "Add new post"
   git push origin main
   ```

2. GitHub Pages builds and deploys within seconds

## Important Notes

- **`_site/` is generated** — Don't commit it; it's auto-generated on build
- **`_config.yml` requires restart** — Changes to config don't auto-reload; restart `jekyll serve`
- **Posts by year** — Posts are organized in `_posts/YYYY/` subdirectories for cleaner organization
- **Baseurl is empty** — Root-relative links use `/path` not `/site/path`

## Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [Chirpy Theme Guide](https://chirpy.cotes.page/)
- [Markdown Cheatsheet](https://www.markdownguide.org/cheat-sheet/)
- [YAML Syntax](https://learn-the-web.algonquindesign.ca/topics/markdown-yaml-cheat-sheet/#yaml)

## License

This site is open source. Feel free to fork and customize for your own use.