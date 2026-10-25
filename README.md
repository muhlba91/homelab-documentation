# Homelab - Documentation

[![](https://img.shields.io/github/license/muhlba91/homelab-documentation?style=for-the-badge)](LICENSE)
[![](https://img.shields.io/github/actions/workflow/status/muhlba91/homelab-documentation/verify.yml?style=for-the-badge)](https://github.com/muhlba91/homelab-documentation/actions/workflows/verify.yml)
[![](https://api.scorecard.dev/projects/github.com/muhlba91/homelab-documentation/badge?style=for-the-badge)](https://scorecard.dev/viewer/?uri=github.com/muhlba91/homelab-documentation)

This repository contains documentation and resources for managing the homelab environment.

## Accessing the Documentation

The documentation site is hosted on GitHub Pages and can be accessed at:

[https://muhlba91.github.io/homelab-documentation/](https://muhlba91.github.io/homelab-documentation/)

## Requirements

- Go (module-aware)
- Hugo (extended)
- Dart Sass
- Node.js

See [Development](#development) for how to install them.

## Development

Tool versions (Go, Node.js, Hugo, Dart Sass) are managed with [mise](https://mise.jdx.dev): run `mise trust` and `mise install` once, then use the usual commands (`hugo ...`).

To start the development server, run:

```bash
hugo server --buildDrafts --disableFastRender
```

## Deployment

Releases are managed via GitHub Actions to automatically deploy the site to GitHub Pages.
