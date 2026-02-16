# Site enhancement plan: positioning for speaking, advisory, and board roles

February 2026. This plan covers what to change on cronyn.co.uk and why, informed by research into Ivan's unique positioning, target conferences, advisory pathways, and comparable career trajectories.

---

## Part 1: What makes you distinctive (and what the site doesn't yet say)

### The three-domain rarity

The research turned up no publicly visible individual who has worked across all three of risk technology, quantitative investment technology, and solutions/bespoke mandate technology within top-tier hedge funds. These domains are deeply siloed. Risk tech people build VaR engines and stress tests. Quant tech people build signal pipelines and backtesting frameworks. Solutions tech people build mandate orchestration and client delivery systems. Most careers stay in one lane.

Your career path - quant team at GLG (under Dr Nicholas Clarke, PhD Computational Mathematics, now MD/Head of Portfolio Management Tech at Man AHL), then risk technology (reporting to Dr Darrel Yawitch, PhD Theoretical Physics, CRO across Man Solutions/AHL/GLG), then Head of Solutions Technology - covers the full value chain from alpha generation through risk management to client delivery. That is CTO-scope thinking demonstrated through doing, not just claimed on a CV.

The site currently says none of this. The About page lists career history as a flat timeline. The risk technology stint and the quant team experience are invisible.

### The practitioner-writer gap

Almost all public writing about AI in financial services comes from vendors, consultancies, regulators, or think tanks. Practitioners inside regulated firms almost never write publicly. The research found only three comparable figures (Danilo McGarry ex-Citi, Dr Paul Dongha, Clara Durodie) - and all three have left their firms for advisory/consulting. You are writing from inside the building. That is your structural advantage, and the site should make it explicit.

### The 45-year programming arc

ZX81 BASIC in Durban (1981) to AI agents in London (2026). Ten major paradigm shifts, experienced as a practitioner. Many people started early. Very few are still hands-on, still leading engineering teams, AND writing substantively about technology deployment. The site mentions the ZX81 in passing on the About page. It does not draw the line from there to here. That line is a keynote talk waiting to happen.

### The South African thread

Both you and Darrel Yawitch are South African. You grew up in Durban; he studied at Wits in Johannesburg. The SA diaspora in London finance is significant and well-networked (SAFFA Breakfast Indaba at Vivat Bacchus near London Bridge, South African Business Club with 450+ members). The site currently mentions Durban once. This is not about making it a brand - it is about recognising a community and network that already exists.

### The contrarian thesis at the right moment

"Trust, not capability" is contrarian in a market obsessed with model benchmarks, but the evidence is catching up. MIT Sloan research confirms people prefer human decisions even when AI performs better. The WEF found 91% of organisations unprepared to scale AI responsibly. Your six essays over nine months are the beginning of a Howard Marks-style body of work. The site presents the essays as a list. It does not yet position the thesis as a coherent intellectual project.

---

## Part 2: Site changes - what to build

### Change 1: Add Open Graph and Twitter Card meta tags to all pages

**Why:** When someone shares an essay on LinkedIn - your primary distribution channel for all three target audiences - it currently renders as a bare URL. No title card, no description, no image. Board recruiters, conference organisers, and senior hiring managers are on LinkedIn. This is the highest-ROI change for zero visual impact.

**What:**
- Add `og:title`, `og:description`, `og:image`, `og:url`, `og:type` to every page
- Add `twitter:card`, `twitter:title`, `twitter:description`, `twitter:image`
- Use the headshot as the default `og:image`; for essays, use the headshot or a site-level card image
- Add `og:site_name` = "Ivan Cronyn"
- Add canonical URL tags (`<link rel="canonical">`) to every page

**Scope:** ~12 lines of HTML per page, 9 pages total.

### Change 2: Create a Speaking page (`/speaking/index.html`)

**Why:** This is the single biggest gap for conference programme committees. They need to decide in minutes whether to invite you. Right now they would have to piece together your positioning from the About page and hope they find the essays. A speaking page is a ready-made speaker kit.

**What the page should contain:**

**Short bio (50 words, copy-pasteable):**
> Ivan Cronyn is a Principal Engineer and Head of Solutions Technology at a major London hedge fund, where he leads engineering for bespoke investment mandates. He has spent 27 years building financial systems across risk, quant, and client technology, and writes about AI deployment in regulated environments.

**Long bio (150 words, for programme booklets):**
> Ivan Cronyn leads engineering for bespoke investment mandates at one of the world's largest alternative investment managers in London. Over 27 years in financial technology - at Barclays Capital, Merrill Lynch, GLG Partners, Brevan Howard, and his current firm - he has built systems across risk technology, quantitative research, and solutions engineering: the full lifecycle from signal generation through risk management to client delivery.
>
> He has programmed since 1981, starting on a Sinclair ZX81 in Durban, South Africa, and has built production systems through every major paradigm shift from structured programming to AI agents. His writing argues that trust, not capability, is the real bottleneck in AI-assisted engineering - that the models are good enough, but systems must be designed to absorb their mistakes cheaply. His essays have been read by [X] (add metric when available).

**Topics I speak on:**
1. **Trust, not capability: what production AI actually needs** - Why the bottleneck in AI adoption is not model quality but the ability to observe, reverse, and enforce AI output. Drawn from building AI-integrated systems inside a regulated financial firm.
2. **Ten paradigm shifts: what 45 years of programming teaches you about AI** - From ZX81 BASIC to AI agents. Pattern recognition across every major technology transition since 1981. What the previous nine shifts tell us about this one.
3. **Bainbridge's ironies, forty years on** - A 1983 paper about factory automation predicted the exact problems we now face with AI coding assistants. What it means for how we build teams.
4. **The suspicion tax: when AI erodes trust faster than it creates value** - Why self-reported AI productivity gains are structurally unreliable, and what to measure instead.
5. **Building engineers when AI writes the code** - Junior developer training in the age of AI. What skills still matter, what formative work looks like now, and why optimising for today's velocity breaks tomorrow's capability.

**Formats:** Keynote, panel, fireside chat. (Note: debating background makes panel/fireside particularly strong - flag this.)

**Downloadable headshot:** Link to a high-resolution version of the existing headshot.

**Contact:** A line with preferred contact method (email or LinkedIn).

**Design:** Same nav, same CSS, same minimal aesthetic as the rest of the site. Add "Speaking" to the nav across all pages.

### Change 3: Strengthen the About page

**Why:** The About page currently reads as a career timeline with a "beyond work" section. It undersells governance-relevant experience. Board recruiters scan for words like "risk", "regulatory", "governance", "accountability". The essays have all of this; the About page has none.

**What to add (not rewrite - add):**

**a) A "What I focus on" section** after the current role description:
- AI deployment in regulated environments - designing systems where AI output can be trusted
- Engineering leadership - building teams that compound capability over years
- Risk and governance in technology - how to absorb errors cheaply, from any source
- Portfolio construction and optimisation technology - the intersection of quant research and engineering

**b) Surface the three-domain experience.** The career timeline currently lists firms. It does not say what you did at each in terms that resonate with boards. Add a line or two per role that surfaces the risk/quant/solutions thread. For example:
- Current role: reference the mandate engineering, multi-engine orchestration, and the breadth across risk, quant, and client technology
- Brevan Howard: front-office development, software architecture, team leadership
- GLG Partners: senior member of the quant team, quantitative analysis and development
- The risk technology stint at Man Group (currently invisible): add it to the timeline

**c) Remove nothing.** The guitar, baking, chess, genealogy details humanise the profile. Keep them.

### Change 4: Add an RSS feed (`/feed.xml`)

**Why:** People who read one essay and want to follow your writing have no mechanism to do so other than checking back manually. An RSS feed is a single static XML file - no JavaScript, no build step, fits the site's constraints perfectly.

**What:** A hand-written XML file with one `<item>` per essay. Update manually when adding new essays. Link to it from every page via `<link rel="alternate" type="application/rss+xml">` in the `<head>`.

### Change 5: Add JSON-LD structured data

**Why:** Search engines cannot currently present you as a Person, your essays as Articles, or your site as a professional profile. When someone searches "AI trust engineering finance speaker", structured data helps you surface.

**What:**
- `Person` schema on the homepage and About page (name, jobTitle, worksFor, url, sameAs for LinkedIn/GitHub)
- `Article` schema on each essay page (headline, datePublished, author, description)
- `WebSite` schema on the homepage

**Scope:** ~20 lines of JSON-LD per page type. No visual change.

### Change 6: Strengthen the Reading page

**Why:** The reading page currently links to an external GitHub repo. Visitors who might invite you to speak or sit on a board will not click through to a GitHub repo. The annotated reading list, brought onto the site, demonstrates intellectual breadth and curatorial judgment - both signals that boards and conference committees value.

**What:** Pull the curated list from the GitHub repo into the page itself. Keep the three trails structure. Add brief annotations for each source. This makes the page a standalone resource rather than a pointer.

### Change 7: Add a contact line

**Why:** Conference organisers and board recruiters may not want to use LinkedIn. A simple `mailto:` link lowers the barrier.

**What:** Add a contact email to the Speaking page and the About page footer. Can be an alias that forwards.

---

## Part 3: Positioning strategy beyond the site

### Conferences to target

Research identified five tiers of conferences where your profile fits. Ordered by relevance:

**Tier 1 - Finance + AI (your home turf)**
- **AI in Financial Services Conference 2026** (Arena International, London) - 500+ senior execs, 2 days. Your "trust, not capability" thesis is directly relevant. Likely CFP-based.
- **RE:WORK AI in Finance Summit** (London) - Mix of academia and industry. Good for the Bainbridge angle.
- **Quant Strats / Future Alpha 2026** (Alpha Events, London) - 600+ quants, PMs, data scientists. The quant-team-to-risk-to-solutions career arc would resonate here.
- **FStech Future of AI in Financial Services 2026** (London) - Covers agentic AI deployment, model risk, infrastructure at scale. Strong fit for "observable, reversible, enforceable".
- **Momentum AI London 2026** (Reuters Events, Canary Wharf) - Senior decision-makers, AI transformation in finance.
- **AI World Congress 2026** (London, June) - Major brands, speakers from Anthropic, Microsoft, IBM.

**Tier 2 - Engineering leadership**
- **LeadDev / LeadingEng** (London and New York) - The premier engineering leadership conference circuit. CFP-based. Strong fit for the "building engineers in the age of AI" talk. LeadDev London is your local event.
- **ELC Conference 2026** (Prague, April) - Central Europe's leading event for engineering leaders. CTOs, VPs, directors. CFP-based.
- **DevExec World** (co-located with DeveloperWeek) - CTO/director level. US-based but high visibility.

**Tier 3 - AI in production**
- **MLOps World / GenAI Summit** (Austin, October) - Production AI deployment focus. CFP-based. Topics include governance, model risk management, agents in production.
- **Machine Learning Week Hybrid AI 2026** (San Francisco, May) - Vendor-neutral, enterprise practitioners only. CFP open. Evaluation favours specific deployment measurements.
- **MLcon** (Berlin, November) - Practical MLOps and production deployment. European.

**Tier 4 - Risk and governance**
- **RiskMinds International** (typically Amsterdam/London) - The premier financial risk conference. CROs, heads of risk, risk technology leaders attend.
- **OpRisk North America / Europe** - Operational risk focused. AI governance is a growing track.
- **FCA/PRA industry events** - Regulators occasionally host practitioner roundtables on technology governance.

**Tier 5 - Broader tech with relevant tracks**
- **QCon London** - Software engineering conference with architecture and AI tracks. Practitioner-focused, high signal.
- **Devoxx UK** (London) - Large developer conference with leadership tracks.
- **NDC London** - .NET/general development conference. C# background is relevant here.

**Recommended format:** Your debating background makes panel discussions and fireside chats your strongest format. These are also the formats that conference organisers struggle most to fill with compelling participants - most speakers want to give prepared talks. Positioning yourself as available for panels on AI governance, engineering leadership, or AI in finance immediately differentiates you from the keynote-or-nothing crowd.

### The speaking ladder

1. **Start with your network.** The SAFFA Breakfast Indaba at Vivat Bacchus (bimonthly, London Bridge) features guest speakers. Low stakes, trust-based audience, SA diaspora network. A talk on AI in London finance, framed through the Durban-to-London arc.
2. **Internal events at your firm.** If you present internally on AI deployment, that is speaking experience you can reference.
3. **Meetups and user groups.** London has active Python, C#, and fintech meetup scenes. A 20-minute talk on Bainbridge's ironies would work at any of them.
4. **Submit to CFPs.** LeadDev London, ELC Prague, and the Arena International AI in Financial Services conference are the highest-value targets for 2026.
5. **Accept panel invitations.** Panels are lower-preparation than keynotes and let your debating skills shine. Say yes to every relevant one.

### Advisory and board pathways

**The NED landscape for technology expertise:**
- UK boards increasingly need technology NEDs, driven by FCA and PRA expectations around operational resilience, cyber risk, and AI governance.
- The SM&CR regime means boards of regulated firms need directors who understand technology risk, not just business risk. Your essays on "observable, reversible, enforceable" and trust infrastructure are directly relevant to this.
- Fintech firms, wealth managers, and smaller asset managers are the most accessible board seats. Large listed companies typically recruit NEDs through headhunters (Odgers Berndtson, Spencer Stuart, Heidrick & Struggles).

**Comparable transitions:**
- Joseph Schull (Warburg Pincus, technology focus) became NED at multiple public companies.
- Elena Sherr (Citibank, Goldman Sachs) moved from investment banking advisory to NED roles through governance expertise developed advising boards.
- Sandy Rattray (ex-Man Group CIO) now sits on the MSCI board as a non-executive director - the clearest precedent from within your firm's orbit.

**Think tanks and advisory bodies to approach:**
- **Alan Turing Institute** - Has practitioner advisory panels on AI in industry. Your "trust, not capability" thesis aligns with their responsible AI work.
- **AI Safety Institute (AISI)** - UK government body. Recruits practitioner advisors on AI deployment in regulated industries.
- **DSIT (Department for Science, Innovation and Technology)** - Runs consultations and expert panels on AI governance. Practitioners from regulated industries are valued.
- **Bank of England / FCA** - Both run roundtables and working groups on AI in financial services. The BoE's "Machine Learning in UK Financial Services" report draws on practitioner input.
- **Oxford-Man Institute** - Man Group's academic partnership with Oxford. Already in your firm's ecosystem.

**Professional bodies:**
- **BCS (British Computer Society)** - Fellowship (FBCS) is available for senior practitioners. Signals professional standing.
- **IET (Institution of Engineering and Technology)** - Fellowship (FIET) for chartered engineers. Carries weight on board CVs.
- **Royal Academy of Engineering** - Fellowship is elected and prestigious. Longer-term goal.

**Credentials that help:**
- **IoD Certificate in Company Direction** - The standard board-readiness qualification in the UK. Signals you are serious about governance, not just technology.
- **FT Board Director Programme** - High-profile, signals intent.
- **Chatham House membership** - Networking rather than credential, but valuable for the advisory network.

---

## Part 4: The model to follow

Three thinkers the site already names as influences map to a strategy:

**Howard Marks** - Build authority through consistent, thesis-driven writing over years. Six essays in nine months is strong momentum. At twelve, the collection becomes referenceable. At twenty, it supports a book proposal. Never chase trends. Let the memos compound.

**Cliff Asness** - Hold a contrarian position publicly, defend it with data, write with personality. "Trust, not capability" is your equivalent of Asness defending value investing through years of underperformance. The position gains authority precisely because you held it while the market was distracted by capability benchmarks.

**Andrew Haldane** - Bridge academic research and institutional practice using plain language and historical depth. Haldane's "The Dog and the Frisbee" speech - arguing that complex systems need simple rules - is structurally identical to your "trust, not capability" argument. The Bainbridge essay already does this.

**What you add that none of them have:** You are still building the systems you write about. Marks runs a fund, not a codebase. Asness has a research team. Haldane was a regulator. You are the engineer AND the writer. That combination is the hardest to replicate and the most credible with technical audiences.

---

## Part 5: Implementation priority

| # | Change | Impact | Effort | Do when |
|---|--------|--------|--------|---------|
| 1 | Open Graph + Twitter Card meta tags | High | Low | Now |
| 2 | Speaking page | High | Medium | Now |
| 3 | Strengthen About page (add risk/quant/solutions, focus areas) | High | Low | Now |
| 4 | Add Speaking to nav across all pages | Medium | Low | Now (with #2) |
| 5 | RSS feed | Medium | Low | Now |
| 6 | JSON-LD structured data | Medium | Low | Now |
| 7 | Canonical URL tags | Low | Low | Now |
| 8 | Strengthen Reading page | Medium | Medium | Next |
| 9 | Contact line on Speaking/About | Medium | Low | Now |

"Now" means: these can be implemented in the current session.
"Next" means: requires content work beyond HTML scaffolding.

---

## Part 6: What the one-line positioning becomes

**Current (implicit from the site):**
"Principal Engineer who writes about AI."

**Proposed (explicit, backed by the site):**
"The practitioner who has built financial systems across risk, quant, and client technology for 27 years - programming since 1981 - now writing from inside a regulated firm about what actually happens when you deploy AI in production."

That is the line that makes conference organisers pause, board recruiters take a second look, and senior hiring managers think "this person has seen things most candidates haven't."

---

## Appendix: Key people referenced

- **Dr Darrel Yawitch** - CRO of Man Solutions, Man AHL, Man GLG. PhD Theoretical Physics (King's College London). BSc Hons (Wits, Johannesburg). Fellow of the Faculty of Actuaries. Previously 10+ years at Investec Bank. Co-authored "Drawdowns" in the Journal of Portfolio Management. South African.
- **Dr Nicholas Clarke** - Managing Director, Head of Portfolio Management Tech at Man AHL. PhD Computational and Applied Mathematics (Southampton). Previously GLG Partners.
- **Gary Collier** - CTO of Man Group since 2001. Member of Executive Committee. Oversees ~230 engineers and data scientists across Alpha Technology and Platform Engineering.
- **Sandy Rattray** - Former CIO of Man Group (retired). Now NED on MSCI board. Previously Goldman Sachs, then headed systematic strategies at GLG. Co-authored *Strategic Risk Management* (Wiley).
