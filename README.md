# qterminator.org site

Static site for qterminator.org, built with [Zola](https://www.getzola.org).

## Local

```sh
zola serve            # live-reload at http://127.0.0.1:1111
zola build            # writes ./public
zola check            # validates links, content, templates
```

## Layout

```
config.toml              site config + base_url
content/
  _index.md              homepage (template = index.html)
  blog/
    _index.md            blog index (template = section.html)
    *.md                 individual posts (template = page.html)
templates/
  base.html              shared shell (nav, footer)
  index.html             homepage
  section.html           blog index
  page.html              individual post
sass/style.scss          compiled to /style.css
.woodpecker.yml          CI: build + push to `pages` branch
```

## Add a post

Create `content/blog/YYYY-MM-DD-slug.md` with frontmatter:

```toml
+++
title = "Post title"
date = 2026-05-14
description = "Short summary for meta tags."
[taxonomies]
tags = ["release"]
+++

Body in markdown.
```

## Deploy (GitHub Pages)

Hosted on GitHub Pages via GitHub Actions. Every push to `main` runs
[`.github/workflows/deploy.yml`](.github/workflows/deploy.yml), which builds the
site with Zola 0.22.1 and publishes it to the `github-pages` environment.
There is no `pages` branch to maintain.

The custom domain (`qterminator.org`) is set in the repository's **Settings -> Pages**.
DNS: point the apex `qterminator.org` at GitHub Pages (A/AAAA records) and set
`www.qterminator.org` as a CNAME to `qterminator.github.io`. Enable *Enforce HTTPS* once the
certificate is provisioned.

## License

GPL-3.0-or-later. See [LICENSE](LICENSE).
