# CLAUDE.md

Guide for AI assistants working with this repository.

## Project Overview

This is **cronyn.co.uk** - Ivan Cronyn's personal website, hosted as a static GitHub Pages site. It serves as a professional landing page, writing portfolio, and hub linking to future subdomain sites.

## Repository Structure

```
cronan.github.io/
├── index.html                  # Landing page
├── styles.css                  # Single stylesheet (dark mode, responsive)
├── CNAME                       # cronyn.co.uk
├── writing/
│   ├── index.html              # Essay listing
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

## Tech Stack

- **Hosting**: GitHub Pages (automatic deployment from default branch)
- **Domain**: `cronyn.co.uk` (via CNAME file; DNS A records point at GitHub Pages IPs)
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
- All pages share the same `nav` structure: Home, Writing, Reading, About
- Essay pages link back to `/writing/` and `/`

## Author

Ivan Cronyn, Principal Engineer & Head of Solutions Technology at Man Group in London. Leads the engineering function for Man Solutions' bespoke investment mandates.

Background: Coding since 1981 (ZX81, Durban, South Africa). Career: Barclays Capital, Merrill Lynch, GLG Partners, Brevan Howard, Man Group. Languages: C++, C#, Python. Twenty-seven years in London finance.

Thesis: "Trust, not capability" - AI is a force multiplier only if systems are designed to absorb mistakes cheaply.

Career goal: Become Man Group's most senior and visible technologist. CTO-track positioning, external recognition through speaking engagements, advisory roles, eventually board positions.

## Voice: Quiet Authority

Write as someone who has built things, seen hype cycles come and go, and knows the difference between signal and noise. Target audience: board nominating committees, conference programme committees, peers at Head of Engineering / CTO level. They've seen thousands of self-promoters. They're screening for judgment.

Characteristics:

- Open with observation, not opinion. Let the reader arrive at the conclusion.
- Use "I" sparingly but deliberately. When personal experience is the evidence, use it. Otherwise, let the argument stand alone.
- Acknowledge complexity without being paralysed by it. "This is genuinely hard. Here's how I think about it."
- Draw on long time horizons. "Over twenty-seven years..." creates implicit authority without claiming it.
- Be specific where it matters, plain otherwise. Technical precision on technical points. Simple language for strategic implications.
- End with implications, not prescriptions. Suggest what thoughtful people should consider. Don't lecture.

This voice sits between practitioner and strategic leader. Technical depth with board-level altitude. Gravitas without pomposity.

Influences to channel: Howard Marks (patient argument, intellectual honesty), Cliff Asness (quant who can write, backs opinions with evidence), Andrew Haldane (institutional voice, translates complexity without dumbing down).

Do not channel: Generic tech leadership content. LinkedIn optimisation. Consultantese. Conference-circuit platitudes.

### Across essays

The essays are a collection, not isolated pieces. Readers who find one will read others. Watch for:

- Vary the shape. Not every essay should follow the same arc (observation, framework, application, restatement). Open some with stories, others with questions, others with data or a direct claim.
- Don't reuse concrete images across essays. "2am production incident" is vivid once; after that, find different details.
- If two essays reach the same conclusion, write the conclusion differently. Same thesis, different words and angle.
- Watch for convergent framing. "The question isn't X, it's Y" is a powerful device once. By the third essay it's a formula.

## Writing Preferences

Use British English (optimisation, colour, behaviour). Mid-Atlantic acceptable for international audiences.

For comprehensive AI pattern detection (37 patterns organised by detection severity), see `.claude/skills/humaniser/SKILL.md`. That skill is portable across repos. What follows here is site-specific.

### House Style

- Em-dashes: never. Use hyphens, commas, or separate sentences.
- Sentence case for headings, not title case.
- No exclamation marks (almost never). No emojis in professional writing.
- "is" over "serves as", "stands as", "acts as" - just use the copula.
- Prefer verbs to nominalisations. "Decide" not "make a decision."
- Active voice. Subject-verb-object.
- Concrete detail over vague claims. "84% exposure" not "significant exposure."

### Banned Words (quick reference)

These words should never appear in content for this site. The humaniser skill has the full list with examples; this is the generation-time checklist.

**Kill on sight:** delve, robust, seamless, nuanced, holistic, comprehensive, pivotal, crucial, testament, vibrant, showcasing, groundbreaking, renowned, leverage (as verb), navigate, landscape (abstract), ecosystem, tapestry, journey (meaning process), framework, paradigm, synergy, unlock, empower, foster, garner, interplay

**Almost always delete:** very, really, extremely, incredibly, deeply, highly, truly, literally, certainly, absolutely, definitely

**Replace with nothing:** Additionally, Furthermore, Moreover, In addition, Consequently, Indeed, As such, Interestingly, Importantly, Notably, Significantly, Crucially, Essentially, Basically

### Structural Patterns to Avoid

- Starting with "So," or "Now," or "Well,"
- Starting with "I" too frequently
- Starting too many sentences with "The" or "This"
- "Here's the thing", "Here's a question", "Here's what" - cut the preamble, start with the substance
- "What's interesting is" or "What's notable is"
- "deep dive" (corporate jargon)
- Rhetorical questions as transitions
- Summarising what was just said
- Bullet points in conversational writing (save for genuinely list-like content)
- Headers in short pieces
- Formulaic section headers: "The broader point", "What this means for X", "The real question", "What X means in practice" - these describe structural roles, not arguments
- Excessive colon usage to introduce explanations
- "Let's" when there's no actual collaboration
- Sentence fragments for false drama. Like this. Every time.
- Parenthetical asides that should be their own sentences
- Numbered lists when prose would work better
- "First,", "Second,", "Third," as mechanical paragraph starters
- Bold-colon inline lists (`**Term:** description`) - convert to flowing prose

### What Good Writing Does

- Varies sentence length dramatically. Short sentences punch. Longer ones can unspool an idea, but sparingly.
- Uses concrete detail and specific numbers.
- Lets silence and implication do work. Trust the reader.
- Has opinions and states them plainly.
- Acknowledges uncertainty where it exists. "I don't know" is a complete sentence.
- Uses first person when personal experience is the evidence.
- Ends on substance, not sentiment.

## Git

- Default branch: `master`
- Commit signing is enabled (SSH key, GPG format)
- Author: configured via global git config
