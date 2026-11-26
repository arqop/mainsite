# ARQOP

The public ARQOP site: a personal archive of cryptocurrency networks, infrastructure notes, and preservation work. It is a best-effort engineering project; it does not promise service uptime.

Live site: [arqop.org](https://arqop.org/)

## What's in this repository

- `content/chains/` contains the network profiles shown in the archive.
- `layouts/` contains the Hugo templates for the home page and chain pages.
- `static/css/` contains the site stylesheets.
- `static/keys/contact@arqop.org.asc` is the public OpenPGP key linked from the contact section. Its fingerprint is `6416 7260 5415 C2F7 DBB6 99E4 496F D08B 7988 DD7D`.

## Run locally

Install [Hugo Extended](https://gohugo.io/installation/). The GitHub Pages workflow currently uses Hugo Extended 0.128.0.

Start the local development server from the repository root:

```sh
hugo server
```

Hugo prints the local preview address, usually `http://localhost:1313/`.

Build the production site locally with:

```sh
hugo --minify
```

The generated site is written to `public/`.

## Publishing

The `Deploy Hugo site to Pages` workflow in `.github/workflows/hugo.yml` builds and deploys the site when changes are pushed to `main`. It can also be run manually from the repository's Actions tab. GitHub Pages uses `https://arqop.org/` as the site base URL; keep it in sync with `hugo.toml`.

For GitHub Pages DNS, the apex domain uses GitHub's A records, and `www` is a DNS-only CNAME to `arqop.github.io`. With both names configured, GitHub Pages redirects `www.arqop.org` to the selected apex custom domain.
