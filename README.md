# Dust Diamond — Computer Science Journey

Personal website documenting my Computer Science learning journey through an online degree program, hands-on projects, and technical certifications.

🔗 **Live site**: [1dgk.github.io](https://1dgk.github.io)

## About

This Jekyll-based site serves as my public notebook for coursework, study notes, project documentation, and reflections on learning CS fundamentals, cybersecurity, networking, and programming. I'm currently pursuing a Bachelor of Computing Science through Thompson Rivers University (distance learning) and working through foundational math courses.

## Content Overview

### Main Sections
- **[Journey](/journey/)** — Curated milestones, degree progress, and study plans
- **[Projects](/projects/)** — Active learning projects and course work (COMP 1131 Java Programming, high school math refresh, past certifications)
- **[Resources](/resources/)** — Curated links to learning platforms, textbooks, tools, and tutorials (networking, Linux, Python, Java, SQL, security)
- **[Notes](/notes/)** — Daily quick notes and observations (separate from blog posts)
- **[Misc](/misc/)** — Books and films (personal reading/watchlists)

### Blog Posts
68+ technical posts covering:
- **Java programming** (COMP 1131 course notes, modules 4-5, quick reference)
- **Cybersecurity** (Google Cybersecurity Certificate series, TryHackMe training plans, CTF writeups)
- **Networking** (CompTIA Network+ notes, CNTp training)
- **Linux** (command-line practice, forensics)
- **Web security** (SQL injection, OWASP, Burp Suite)

Browse by topic using [Categories](/categories/) and [Tags](/tags/).

## Key Milestones

- ✅ **Google Cybersecurity Certificate** (2024) — [Notes index](/posts/gcc-course-index/)
- ✅ **Stanford Code in Place** — [Course index](/posts/code-in-place-index/)
- ✅ **CompTIA Network+ training** — [Network+ notes](/posts/network-plus/)
- 🔄 **TRU COMP 1131** (Java Programming 1) — in progress (Winter 2026)
- 🔄 **High school math refresh** — working through Grade 10-12 courses (MPM2D → MCV4U)

## Tech Stack

- **Site generator**: Jekyll with [Chirpy theme](https://github.com/cotes2020/jekyll-theme-chirpy)
- **Hosting**: GitHub Pages
- **Content**: Markdown files in `_posts/`, `_notes/`, and `_tabs/`
- **Plugins**: jekyll-feed, jekyll-seo-tag, jekyll-sitemap, jekyll-paginate, jekyll-archives

## Local Development

```bash
# Install dependencies
bundle install

# Serve with live reload
bundle exec jekyll serve --livereload

# Build static site
bundle exec jekyll build
```

Site will be available at `http://127.0.0.1:4000/`

**Note**: Changes to `_config.yml` require restarting the Jekyll server.

## Repository Structure

```
├── _config.yml          # Site configuration
├── _posts/              # Blog posts organized by year
│   ├── 2023/
│   ├── 2024/
│   ├── 2025/
│   └── 2026/
├── _notes/              # Daily notes collection (YYYY-MM-DD.md)
├── _tabs/               # Main navigation pages
├── _drafts/             # Unpublished content
├── assets/              # Images, CSS, static files
└── _site/               # Generated site (do not edit)
```

## Notes Collection

The site includes a custom Jekyll collection (`_notes/`) for quick daily observations separate from formal blog posts. Notes:
- Use `YYYY-MM-DD.md` filename format
- Appear at `/notes/` grouped by month/year
- Are excluded from RSS feed and main posts listing
- Use minimal front matter (layout, date)

## Content Policy

- **RSS feed**: Blog posts only (notes excluded)
- **Navigation**: About, Categories, and Tags pages hidden via CSS
- **Drafts**: Stored in `_drafts/` and not published to live site

## Connect

- **GitHub**: [@1dgk](https://github.com/1dgk)
- **Website**: [1dgk.github.io](https://1dgk.github.io)

## License

Content is personal educational documentation. Code examples and configurations are available for reference under standard GitHub terms.