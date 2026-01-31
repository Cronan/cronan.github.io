# CLAUDE.md

Guide for AI assistants working with this repository.

## Project Overview

This is a **static GitHub Pages site** served at `cronan.github.io`. It contains plain HTML with no build step, framework, or dependencies.

## Repository Structure

```
cronan.github.io/
└── index.html          # Site entry point (static HTML)
```

## Tech Stack

- **Hosting**: GitHub Pages (automatic deployment from default branch)
- **Content**: Plain HTML — no templating engine, CSS framework, or JavaScript
- **Build**: None — files are served as-is

## Development Workflow

1. Edit HTML files directly
2. Commit and push to the default branch (`master`)
3. GitHub Pages deploys automatically — no CI/CD pipeline or build step

There is no local dev server configured. To preview locally, open `index.html` in a browser.

## Conventions

- No package manager or dependency files exist — do not introduce `package.json`, `Gemfile`, etc., unless explicitly requested
- No Jekyll — there is no `_config.yml`; GitHub Pages serves raw static files
- Keep changes minimal and avoid adding unnecessary tooling

## Git

- Default branch: `master`
- Commit signing is enabled (SSH key, GPG format)
- Author: configured via global git config
