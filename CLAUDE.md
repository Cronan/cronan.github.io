# CLAUDE.md

Guide for AI assistants working with this repository.

## Project overview

**cronyn.co.uk** - Ivan Cronyn's personal website. Static GitHub Pages site. Professional landing page, writing portfolio, hub for future subdomain sites.

## Repository structure

```
cronan.github.io/
├── index.html                  # Landing page
├── styles.css                  # Single stylesheet (dark mode, responsive)
├── CNAME                       # cronyn.co.uk
├── writing/
│   ├── index.html              # Essay listing
│   ├── compromised-witnesses.html
│   ├── observable-reversible-enforceable.html
│   ├── the-suspicion-tax.html
│   ├── ironies-of-automation.html
│   ├── trust-not-capability.html
│   └── ai-as-junior-engineer.html
├── reading/
│   └── index.html              # Reading list
├── about/
│   └── index.html              # Full bio
├── images/
│   ├── ivan-glitch.jpg         # Home page headshot
│   └── ivan-headshot.jpg       # About page headshot
├── drafts/                     # Unpublished working files
├── .claude/
│   └── skills/
│       └── humaniser/
│           └── SKILL.md        # AI pattern detection (portable)
└── CLAUDE.md                   # This file
```

## Tech stack

GitHub Pages, plain HTML + CSS. No framework, no JavaScript, no build step, no templating engine. Files served as-is. Domain via CNAME; DNS A records point at GitHub Pages IPs.

## Development workflow

Edit HTML directly. Commit and push to `master`. GitHub Pages deploys automatically.

To preview locally, open `index.html` in a browser.

## Conventions

- No package manager, no dependency files. Do not introduce `package.json`, `Gemfile`, etc.
- No Jekyll. No `_config.yml`. Raw static files.
- No JavaScript unless there is no other way.
- Keep changes minimal. Do not add tooling.
- British English throughout (optimisation, colour, behaviour).
- All pages share the same nav: Home, Writing, Reading, About.
- Essay pages link back to `/writing/` and `/`.

## Subdomain architecture (planned)

Other subdomains will be separate repos, each with their own CNAME:

|Subdomain            |Purpose                               |
|---------------------|--------------------------------------|
|`cronyn.co.uk`       |This repo - professional hub + writing|
|`family.cronyn.co.uk`|Genealogy                             |
|`bake.cronyn.co.uk`  |Sourdough, recipes, kitchen notes     |
|`music.cronyn.co.uk` |Guitar, playlists                     |
|`chess.cronyn.co.uk` |Puzzles, games, openings              |

## Design

Monospaced headings (SF Mono / Consolas), serif body (Charter / Georgia). Automatic dark mode via `prefers-color-scheme`. Max width 640px. No images on the landing page. Fast, accessible, printable. Accent colour: dark red (`#8b0000` light, `#c44` dark).

-----

## Author

Ivan Cronyn. Principal Engineer, Head of Solutions Technology at a large systematic and discretionary investment manager in London. Leads engineering for bespoke investment mandates across three business engines.

Coding since 1981 (ZX81, Durban, South Africa). Career: Barclays Capital, Merrill Lynch, GLG Partners, Brevan Howard, then current firm. Languages: C++, C#, Python. Twenty-seven years in London finance.

Writing should not name the firm. Write about principles, not specifics. This constraint is deliberate - it forces universal applicability.

-----

## Voice

The voice is the most important thing in this repository. Get this wrong and nothing else matters.

### Who is reading

Board nominating committees. Conference programme committees. Peers at Head of Engineering and CTO level. They have seen thousands of self-promoters. They are screening for judgment, not credentials.

### How it should sound

Write as someone who has built things, seen hype cycles come and go, and knows the difference between signal and noise. The tone sits between practitioner and strategic leader. Technical depth with board-level altitude. Gravitas without pomposity.

Iain M Banks is the tonal reference - the philosophical, literary Scottish voice, not the sci-fi. Wry, precise, unhurried. The kind of prose where you trust the writer before you agree with them.

Other influences: Howard Marks (patient argument, intellectual honesty), Cliff Asness (quant who can write, backs opinions with evidence), Andrew Haldane (institutional voice, translates complexity without dumbing down).

### Principles

- **Open with observation, not opinion.** Let the reader arrive at the conclusion.
- **Use "I" sparingly but deliberately.** When personal experience is the evidence, use it. Otherwise, let the argument stand alone.
- **Acknowledge complexity without paralysis.** "This is hard. Here is how I think about it."
- **Draw on long time horizons.** Twenty-seven years creates implicit authority without claiming it.
- **Be specific where it matters, plain otherwise.** Technical precision on technical points. Simple language for strategic implications.
- **End with implications, not prescriptions.** Don't lecture.
- **State opinions plainly.** Hedging erodes authority. "I think X" is stronger than presenting both sides without committing.
- **Acknowledge uncertainty where it exists.** "I don't know" is a complete sentence.

### What this voice is not

Generic tech leadership content. LinkedIn optimisation. Consultantese. Conference-circuit platitudes. The voice of someone trying to sound important. The voice of someone who has read about things but not done them.

-----

## The essays as a collection

The essays are a body of work. Readers who find one will read others. The collection must read as if a single person wrote it over months, not as if a model generated each piece from a similar prompt.

### Thesis

"Trust, not capability" - AI is a force multiplier only if systems are designed to absorb mistakes cheaply. Every essay connects to this thesis, directly or at an angle.

### Published essays (chronological)

1. **Building engineers in the age of AI** (May 2025) - junior engineer development
1. **Trust, not capability** (July 2025) - the foundational thesis
1. **Bainbridge's Ironies of Automation, forty years on** (August 2025) - historical grounding
1. **The Suspicion Tax** (November 2025) - the cost of not trusting AI output
1. **Observable, Reversible, Enforceable** (December 2025) - practical framework
1. **Compromised Witnesses** (February 2026) - cognitive bias in AI productivity claims

### Cross-essay discipline

These checks matter more than any single-essay edit. Run them when adding or revising any essay.

**Structural variety.** Not every essay should follow the same arc. If the last three opened with observation, open the next with data, a story, or a direct claim. If they all end with implications, try ending one on a question or an admission of not knowing.

**No shared sentences.** If two essays reach the same conclusion, the conclusion must be written differently. Same thesis, different words and angle. Grep for near-identical phrases across files.

**No recycled images.** A concrete detail used once is an anecdote. Used across four essays it is a verbal tic. "2am production incident" is vivid once. After that, find different details from a different part of the author's experience.

**No convergent framing.** "The question isn't X, it's Y" is a powerful device. Once. By the third essay it is a formula. Keep one instance, rewrite the rest.

**Varied openings.** The clean, contextualising first sentence is an AI tell. Some essays should start mid-thought, or with a reference to something specific, or with a sentence that only makes sense after reading the next two.

-----

## House style

- Em dashes: never. Use hyphens, commas, or separate sentences.
- Sentence case for headings, not Title Case.
- No exclamation marks (almost never). No emojis.
- "is" over "serves as", "stands as" - just use the copula.
- Prefer verbs to nominalisations. "Decide" not "make a decision."
- Active voice. Subject-verb-object.
- Concrete numbers over vague claims. "84%" not "significant."
- Straight quotes, not curly.
- British English. Mid-Atlantic acceptable for international audiences.

-----

## AI pattern detection

**Read `.claude/skills/humaniser/SKILL.md` before writing or editing any content for this site.** The humaniser skill is the single source of truth for AI pattern detection: 37 patterns organised by severity tier, corpus-level checks, vocabulary and structural tells, before/after examples, and process guidance.

This CLAUDE.md does not duplicate that material. Voice, house style, and cross-essay discipline live here because they are site-specific. Pattern detection lives in the skill because it is portable across repos.

-----

## Git

Default branch: `master`. Commit signing enabled (SSH key, GPG format).
