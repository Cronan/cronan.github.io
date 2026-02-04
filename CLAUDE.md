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

## Writing Preferences

Use British English (optimisation, colour, behaviour). Mid-Atlantic acceptable for international audiences.

### Patterns to Avoid

**Significance inflation:** crucial, pivotal, critical, vital, essential, paramount, fundamental, testament, cornerstone, bedrock, incredible, remarkable

**Promotional language:** vibrant, showcasing, groundbreaking, renowned, cutting-edge, game-changing, best-in-class, world-class, leading, premier, innovative, transformative

**AI vocabulary:** Additionally, delve, interplay, underscore, foster, garner, leverage (as verb), navigate, landscape, tapestry, ecosystem, space (meaning industry), journey (meaning process), unlock, empower, unpack, align, synergy

**Intensifiers (almost always delete):** very, really, extremely, incredibly, deeply, highly, particularly, especially, certainly, absolutely, definitely, truly, literally

**Adverb frontloading:** Interestingly, Importantly, Notably, Significantly, Crucially, Frankly, Honestly, Ultimately, Essentially, Basically

**Vague quantifiers (use specific numbers):** a number of, various, significant, substantial, considerable, numerous, countless, myriad

**Hedging and filler:** It's worth noting, It's important to consider, It bears mentioning, That said, With that in mind, At the end of the day, When all is said and done, Moving forward, Going forward, It could be argued that, One might say that

**Bureaucratic bloat:** in order to (use "to"), due to the fact that (use "because"), in the event that (use "if"), prior to (use "before"), subsequent to (use "after"), at this point in time (use "now"), has the potential to (use "could"), is able to (use "can"), make use of (use "use"), with respect to, in terms of, when it comes to, in the context of

**Copula avoidance:** "serves as", "stands as", "acts as", "functions as" - just use "is"

**Parallelism cliches:** "not only... but also", "it's not just... it's", "both X and Y", forced rule of three

**Weak transitions:** Furthermore, Moreover, In addition, Consequently, Thus, Hence, Therefore (at sentence start), However (at sentence start, overused), Indeed, As such

**Redundant signposting:** As mentioned, As noted, As stated, It should be noted that, This is because, The reason is that, In other words, To put it simply, Let me explain

**Presumptuous phrases:** As we all know, Needless to say, It goes without saying, Obviously, Clearly, Of course

**Meta-commentary:** This is a great question, Let me explain, I'd be happy to, Great point, That's an interesting question

**Performative enthusiasm:** Excited to, Thrilled to, Passionate about, Love to see, Can't wait to

**Sycophantic affirmations:** Absolutely, Certainly, Definitely, Of course, Great question, Excellent point

**Generic conclusions:** Exciting times ahead, The future is bright, Only time will tell, Watch this space, Food for thought, Time will tell

**Overused "smart" words:** robust, seamless, nuanced, holistic, comprehensive, strategic, key (as adjective), actionable, impactful, framework, paradigm

**Vague endings:** etc., and so on, among others, to name a few, and the like

### Structural Patterns to Avoid

- Em-dashes. Use hyphens, commas, or separate sentences. Never use the em-dash character.
- Starting with "So," or "Now," or "Well,"
- Starting with "I" too frequently
- Starting too many sentences with "The" or "This"
- "Here's the thing" or "The thing is"
- "What's interesting is" or "What's notable is"
- Rhetorical questions as transitions
- Summarising what was just said
- Bullet points in conversational writing (save for genuinely list-like content)
- Headers in short pieces
- Excessive colon usage to introduce explanations
- Exclamation marks (almost never)
- Emojis (never in professional writing)
- "Let's" when there's no actual collaboration
- Sentence fragments for false drama. Like this. Every time.
- Parenthetical asides that should be their own sentences
- Numbered lists when prose would work better
- "First,", "Second,", "Third," as mechanical paragraph starters

### What Good Writing Does

- Varies sentence length dramatically. Short sentences punch. Longer ones can unspool an idea, but sparingly.
- Uses concrete detail and specific numbers. "84% exposure" not "significant exposure."
- Lets silence and implication do work. Trust the reader.
- Has opinions and states them plainly.
- Acknowledges uncertainty where it exists. "I don't know" is a complete sentence.
- Uses first person when personal experience is the evidence.
- Prefers active voice. Subject-verb-object.
- Prefers verbs to nominalisations. "Decide" not "make a decision."
- Ends on substance, not sentiment.

### Humaniser Skill

For comprehensive AI pattern detection and removal, see `.claude/skills/humaniser/SKILL.md`. Use this skill when editing or reviewing text to catch patterns that might have slipped through.

## Git

- Default branch: `master`
- Commit signing is enabled (SSH key, GPG format)
- Author: configured via global git config
