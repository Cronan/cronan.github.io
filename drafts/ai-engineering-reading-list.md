# ai-engineering-reading-list

A curated reading list on AI in production engineering. Not comprehensive. These are the papers, posts, and talks that have shaped how I think about the problem.

## The foundational problem

**Lisanne Bainbridge, [Ironies of Automation](https://www.ise.ncsu.edu/wp-content/uploads/2020/02/Bainbridge_1satisficer983_Ironies-of-front.pdf)** (1983)

Written about industrial process control, but maps precisely onto AI-assisted software development. The core insight: the more advanced the automation, the more critical the human contribution, and the less likely humans are able to provide it. If you read one thing on this list, read this.

**Gary Klein, [Sources of Power: How People Make Decisions](https://mitpress.mit.edu/9780262534291/sources-of-power/)** (1998)

How experts actually make decisions under pressure. Not through analysis, but through pattern recognition built from experience. Relevant because AI changes how engineers build that pattern recognition.

## Trust and verification

**Leslie Lamport, [Time, Clocks, and the Ordering of Events in a Distributed System](https://lamport.azurewebsites.net/pubs/time-clocks.pdf)** (1978)

Not about AI, but about the fundamental problem of knowing what happened and in what order. Relevant to any system where you need to understand and audit automated behaviour.

**Charity Majors, [Observability Engineering](https://info.honeycomb.io/observability-engineering-oreilly-book-2022)** (2022)

The practical guide to building systems you can actually understand in production. The "observable" in "observable, reversible, enforceable" owes a lot to this.

## AI in practice

**Simon Willison, [simonwillison.net](https://simonwillison.net/)**

Nobody documents their AI usage more thoroughly. His TILs and link blog are a running record of what works and what doesn't. Worth following.

**Andrej Karpathy, [Software 2.0](https://karpathy.medium.com/software-2-0-a64152b37c35)** (2017)

The framing that code is being replaced by data. Written before LLMs, but sets up the question: if the code writes itself, what does the programmer do?

**Dan McKinley, [Choose Boring Technology](https://mcfunley.com/choose-boring-technology)** (2015)

Not about AI, but about the cost of novelty. Useful counterweight when everyone wants to adopt the latest model.

## Financial services context

**Andrew Haldane, [The Dog and the Frisbee](https://www.bankofengland.co.uk/speech/2012/the-dog-and-the-frisbee)** (2012)

Bank of England speech on complexity in financial regulation. The argument: simple rules often outperform complex models. Relevant to thinking about where AI helps and where it doesn't.

**Man Group Research, [Machine Learning Papers](https://www.man.com/maninstitute/)**

The Oxford-Man Institute publishes good work on machine learning in finance. Worth browsing.

## My own writing

- [Trust, not capability: the real bottleneck in AI-assisted engineering](https://cronyn.co.uk/writing/trust-not-capability.html)
- [Building engineers in the age of AI](https://cronyn.co.uk/writing/ai-as-junior-engineer.html)
- [Bainbridge's Ironies of Automation, forty years on](https://cronyn.co.uk/writing/ironies-of-automation.html)

---

## About this list

I'm [Ivan Cronyn](https://cronyn.co.uk), Principal Engineer & Head of Solutions Technology at Man Group. This list reflects what I've found useful thinking about AI in production financial software. It's not comprehensive and it's not neutral. These are the things that shaped my thinking.

Suggestions welcome via issues or pull requests.

---

## Notes on this draft

**Structure:**
- Thematic sections, not a flat list
- Each entry has author, title, year, and a sentence on why it matters
- My own essays go at the end, not the top
- Credits authors by name (Simon Willison approach)
- "About this list" section at the end establishes credibility

**Voice check:**
- "Not comprehensive" (acknowledges limitations)
- "If you read one thing on this list, read this" (has opinions)
- "Useful counterweight" (shows thinking, not just listing)
- No promotional language for own work
- British spelling throughout

**What to add over time:**
- More entries as you read them
- Maybe a "Recently added" section
- Could add a `/talks` section for conference talks

**Humaniser check:**
- No "crucial" or "pivotal"
- No "serves as" or "stands as"
- No rule of three
- Em dashes: only 2 in the whole document
- First person, direct
