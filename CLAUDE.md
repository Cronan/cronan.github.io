# CLAUDE.md

Guide for AI assistants working with this repository.

## Project overview

**cronyn.co.uk** - Ivan Cronyn's personal website. Static GitHub Pages site. Professional landing page, writing portfolio, hub for future subdomain sites.

## Repository structure

Run `ls` for the current layout; a listing written here would only go stale (the one that was here did). The files whose purpose is not obvious from their names:

- `drafts/` - unpublished working files, never linked from the site
- `CONTEXT.md` - source material gathered for the "672 bytes" essay
- `VOICE-GUIDE.md` - standalone voice guide; overlaps with the Voice section below
- `.claude/skills/humaniser/SKILL.md` - AI pattern detection skill (portable across repos)
- `feed.xml`, `sitemap.xml` - maintained by hand; see the essay checklist below

## Tech stack

GitHub Pages, plain HTML + CSS, plus a few lines of inline JavaScript per page (scroll-reveal). No framework, no build step, no templating engine. Files served as-is. Domain via CNAME; DNS A records point at GitHub Pages IPs.

## Development workflow

Edit HTML directly. Commit and push to `master`. GitHub Pages deploys automatically. To preview locally, open `index.html` in a browser.

There is no build step, no test suite, and no CI. Validation is visual: open the page in a browser and check it looks right.

## Adding an essay

This has been forgotten before, most recently by missing the landing page. Do not work from a remembered file list, including the one below. The check that actually catches omissions:

**Grep for the previous essay's filename. Every file it appears in, except its own page, needs the new essay too.** Run the same grep for the new essay afterwards and compare.

For orientation, the current set is six files: the essay page itself, the essay lists in both `writing/index.html` (HTML and JSON-LD) and the landing page `index.html`, `llms.txt`, plus `feed.xml` and `sitemap.xml` (new entry, and `lastmod` for `/` and `/writing/`). The grep is authoritative; this list is not.

## Conventions

- No package manager, no dependency files. Do not introduce `package.json`, `Gemfile`, etc.
- No Jekyll. No `_config.yml`. Raw static files.
- No JavaScript unless there is no other way.
- Keep changes minimal. Do not add tooling.
- British English throughout (optimisation, colour, behaviour).
- All pages share the same nav. When adding a page, copy the nav from an existing page, not from any list written down here.
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

Monospaced headings (SF Mono / Consolas), serif body (Charter / Georgia). Automatic dark mode via `prefers-color-scheme`. Max width 640px. Fast, accessible, printable. Accent colour: dark red (`#8b0000` light, `#c44` dark). Social share card: `images/og-card.png` (1200x630), referenced by every page's `og:image`; regenerate in the same typographic style if the thesis line or name treatment changes. Favicons: `favicon.ico`, `favicon-32.png`, `apple-touch-icon.png` at the repo root (the ZX81 K cursor: accent-red ground, off-white mono K), linked from every page's head.

-----

## Author

Ivan Cronyn. Principal Engineer, Head of Solutions Technology at Man Group in London. Leads engineering for bespoke investment mandates across three business engines.

Coding since 1981 (ZX81, Durban, South Africa). Career: Barclays Capital, Merrill Lynch, GLG Partners, Brevan Howard, then Man Group. Languages: C++, C#, Python. In London finance since 1998.

Essay bodies do not name the firm; the standard footer byline, the bio pages, and the README do. Write about principles, not firm specifics. This constraint is deliberate - it forces universal applicability.

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
- **Draw on long time horizons.** A career in production finance since 1998 creates implicit authority without claiming it.
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

### Published essays

The canonical list, with dates and descriptions, is `writing/index.html`. Do not rely on any list of essays written down here or elsewhere; an earlier copy in this file went stale and caused planning against a six-essay collection when there were nine. Before adding or revising an essay, read the index and skim the most recent two or three essays in full - the cross-essay checks below depend on knowing what the collection currently says.

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
- Anchor durations to a start year, never a count: "since 1998", not "27 years". Counts silently go stale; the site has already shipped a wrong one. (Essays are dated artefacts - a count correct at publication stays.)
- Straight quotes, not curly.
- British English. Mid-Atlantic acceptable for international audiences.

-----

## AI pattern detection

**Read `.claude/skills/humaniser/SKILL.md` before writing or editing any content for this site.** The humaniser skill is the single source of truth for AI pattern detection: 37 patterns organised by severity tier, corpus-level checks, vocabulary and structural tells, before/after examples, and process guidance.

This CLAUDE.md does not duplicate that material. Voice, house style, and cross-essay discipline live here because they are site-specific. Pattern detection lives in the skill because it is portable across repos.

-----

## Git

Default branch: `master`. Commit signing enabled (SSH key, GPG format).
