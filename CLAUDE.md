# CLAUDE.md

Guide for AI assistants working with this repository.

## Project Overview

This is **cronyn.co.uk** - Ivan Cronyn's personal website, hosted as a static GitHub Pages site. It serves as a professional landing page, writing portfolio, and hub linking to future subdomain sites.

## Repository Structure

```
cronan.github.io/
├── index.html              # Landing page - career front and centre
├── styles.css              # Single stylesheet (dark mode, responsive)
├── writing/
│   ├── index.html          # Essay listing
│   ├── trust-not-capability.html
│   ├── ai-as-junior-engineer.html
│   └── ironies-of-automation.html
├── about/
│   └── index.html          # Full bio
└── CLAUDE.md               # This file
```

## Tech Stack

- **Hosting**: GitHub Pages (automatic deployment from default branch)
- **Domain**: `cronyn.co.uk` (CNAME removed temporarily - re-add `CNAME` file containing `cronyn.co.uk` once DNS A records are pointed at GitHub Pages IPs)
- **Content**: Plain HTML + CSS - no templating engine, framework, or JavaScript
- **Build**: None - files are served as-is

## Subdomain Architecture (planned)

Other subdomains will be separate GitHub repos, each with their own CNAME:

| Subdomain | Purpose |
|---|---|
| `cronyn.co.uk` | This repo - professional hub + writing |
| `family.cronyn.co.uk` | Genealogy - Cronyn & family history |
| `bake.cronyn.co.uk` | Sourdough, recipes, kitchen notes |
| `music.cronyn.co.uk` | Kommandanten, guitar, playlists |
| `chess.cronyn.co.uk` | Puzzles, games, openings |

## Design Principles

- Monospaced headings (SF Mono / Consolas), serif body (Charter / Georgia)
- Automatic dark mode via `prefers-color-scheme`
- Max width 640px, generous whitespace
- No images on the landing page - text does the work
- Fast, accessible, printable
- Accent colour: dark red (`#8b0000` light, `#c44` dark)

## Development Workflow

1. Edit HTML files directly
2. Commit and push to the default branch (`master`)
3. GitHub Pages deploys automatically - no CI/CD pipeline or build step

To preview locally, open `index.html` in a browser.

## Conventions

- No package manager or dependency files - do not introduce `package.json`, `Gemfile`, etc.
- No Jekyll - there is no `_config.yml`; GitHub Pages serves raw static files
- No JavaScript unless strictly necessary
- Keep changes minimal and avoid adding unnecessary tooling
- British English spelling throughout (optimisation, colour, behaviour)
- All pages share the same `nav` structure: Home, Writing, About
- Essay pages link back to `/writing/` and `/`

## Content Context

Ivan Cronyn is a Principal Engineer & Head of Solutions Technology at Man Group. His writing focuses on AI in production engineering, trust vs capability, and engineering leadership. The site's tone is measured, authoritative, and grounded - not hype-driven.

## Git

- Default branch: `master`
- Commit signing is enabled (SSH key, GPG format)
- Author: configured via global git config
