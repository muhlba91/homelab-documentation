# Homelab - Documentation

[![](https://img.shields.io/github/license/muhlba91/homelab-documentation?style=for-the-badge)](LICENSE)
[![](https://img.shields.io/github/actions/workflow/status/muhlba91/homelab-documentation/verify.yml?style=for-the-badge)](https://github.com/muhlba91/homelab-documentation/actions/workflows/verify.yml)
[![](https://api.scorecard.dev/projects/github.com/muhlba91/homelab-documentation/badge?style=for-the-badge)](https://scorecard.dev/viewer/?uri=github.com/muhlba91/homelab-documentation)

This repository contains documentation and resources for managing the homelab environment.

## Accessing the Documentation

The documentation site is hosted on GitHub Pages and can be accessed at:
[https://muhlba91.github.io/homelab-documentation/](https://muhlba91.github.io/homelab-documentation/)

## Requirements

- Go 1.18+ (module-aware)
- Hugo

## Development

To start the development server, run:

```bash
hugo server --buildDrafts --disableFastRender
```

## Deployment

Releases are managed via GitHub Actions to automatically deploy the site to GitHub Pages.
