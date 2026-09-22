# AGENTS.md

## Project

Static Jekyll site for Mark IJbema, a software consultant helping engineering teams improve their development process,
including AI tooling adoption.

This is hosted at `https://ijbema.com` as a custom domain on GitHub Pages.

- URL: `https://ijbema.com`
- Repository: `markijbema/ijbema_com`

## Constraints

- Use Jekyll only; no Node build step, Tailwind, JavaScript framework, GitHub Actions build, or custom plugins.
- Keep pages as Markdown with front matter.
- Keep shared header/footer/navigation in `_includes/` and layouts in `_layouts/`.
- Keep styling in `assets/css/style.css` using plain responsive CSS.
- Use `relative_url` for internal links so the configured GitHub Pages base URL works.
- Do not invent specific consulting claims, clients, metrics, or experience.
- Leave `[PLACEHOLDER: ...]` text in place unless the user has provided replacement content.

## Commands

```sh
zsh -lic 'bundle install'
zsh -lic 'bundle exec jekyll build'
zsh -lic 'bundle exec jekyll serve --livereload'
```

Run all Ruby, Bundler, and Jekyll commands through `zsh -lic` from the repository root. The tool shell does not
initialize rbenv and otherwise resolves the system `/usr/bin/ruby`; do not invoke `ruby` or `bundle` directly from the
non-interactive tool shell.

The project expects Ruby 3.3.4 from `.ruby-version` and Bundler 2.5.11. Verify the active toolchain with
`zsh -lic 'rbenv version && ruby -v && bundle -v'`.

LiveReload refreshes the browser after regeneration completes.

## Structure

- `_config.yml` — site settings, navigation defaults, base URL
- `_layouts/` — HTML layouts for pages and posts
- `_includes/` — shared header and footer
- `_posts/` — blog posts named `YYYY-MM-DD-title.md`
- `assets/css/style.css` — site styling
- `index.md`, `about.md`, `blog.md`, `contact.md` — main pages

## Notes

- `Gemfile` pins `github-pages` version 232 for GitHub Pages compatibility.
- `bigdecimal` and `csv` are included for newer Ruby compatibility.
- Blog posts can be added by dropping a correctly named Markdown file into `_posts/`.
