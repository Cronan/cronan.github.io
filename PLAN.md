# Plan: humanise the writing and improve the detection tooling

Temporary file. Delete after executing.

---

## Context

A review of all five essays and the site pages identified patterns that flag
as AI-generated, cross-referencing:

- The humaniser skill (`.claude/skills/humaniser/SKILL.md`) - 24 patterns from Wikipedia
- CLAUDE.md writing preferences - ~20 categories of banned vocabulary and structural patterns
- 2025-2026 research on AI text detection (lexical diversity, sentence-length uniformity, punctuation distribution, reasoning-model tells)

The three sources don't fully overlap, and none of them covers the patterns
that only show up when you read a collection of essays together rather than
one at a time.

---

## 1. Upgrade the humaniser skill

The skill currently handles single-text pattern detection. The biggest tells
from this review were corpus-level patterns: identical phrases across essays,
overused motifs, structural homogeneity. These need their own section.

### 1a. Add "Corpus-level patterns" section to SKILL.md

New patterns to document with examples:

- **Cross-text verbatim repetition.** LLMs converge on the same conclusion
  for similar prompts. If two essays by the same author share a near-identical
  paragraph, one of them was almost certainly generated. Example from this
  review: the "firms that adopt it fastest" conclusion appeared in two essays.

- **Motif overuse across a body of work.** A concrete image used once is an
  anecdote. Used twice is a callback. Used four or five times across five
  essays (like "2am" in this collection) is a verbal tic that betrays
  generation-per-prompt rather than writing-across-a-lifetime.

- **Structural homogeneity.** All five essays follow the same rhetorical arc:
  observation, framework, financial-services application, closing restatement.
  A human writing on related topics over months would naturally vary the shape.
  One essay could open with a story. Another with data. Another with a
  question. The sameness of structure is itself a tell.

- **Convergent framing.** The "question isn't X, it's Y" negative-parallelism
  framing appeared in four of five essays. Any rhetorical device used that
  densely across a collection signals a single generation style, not a human
  voice developing over time.

### 1b. Add patterns from CLAUDE.md that the skill currently lacks

The skill and CLAUDE.md were built independently and have gaps in both
directions. These CLAUDE.md categories should be added to the skill (they
apply to any writing, not just this repo):

- Intensifiers (very, really, extremely, incredibly...)
- Adverb frontloading (Interestingly, Importantly, Notably...)
- Bureaucratic bloat (in order to, due to the fact that...)
- Weak transitions (Furthermore, Moreover, In addition...)
- Redundant signposting (As mentioned, As noted...)
- Overused "smart" words (robust, seamless, nuanced, holistic, framework...)
- Vague endings (etc., and so on, among others...)

### 1c. Add patterns from 2025-2026 research

New findings that neither document covers:

- **Lower lexical diversity.** AI text uses fewer unique words than human text
  of the same length. If a passage reads as syntactically varied but
  vocabularily narrow, investigate.

- **Uniform sentence length.** Human writing has high variance in sentence
  length. AI text clusters around a mean. Look for passages where every
  sentence is 15-25 words.

- **Punctuation poverty.** AI text over-relies on commas and periods. Human
  text uses more semicolons, colons, parentheses, question marks, and
  (outside this repo's style rules) em dashes. If the punctuation is
  exclusively commas and periods, that's a soft signal.

- **"Here's" constructions.** "Here's a question", "Here's what gets me",
  "Here's the thing" - reasoning models use these as transition devices. The
  skill already covers "Here's the thing" via CLAUDE.md but should flag the
  broader pattern.

- **Formulaic section headers.** "The broader point", "What this means for X",
  "Looking ahead", "The real question" - these signal a model organising
  output into a predictable structure rather than a writer finding the
  natural shape of an argument.

### 1d. Add a "reviewing a collection" checklist

When the skill is invoked on a set of related texts (like an essay
collection), add this process step:

1. Grep for phrases that appear in more than one file
2. Check whether concrete images/anecdotes recur across pieces
3. Compare the structural arc of each piece - are they all shaped the same?
4. Look for identical rhetorical devices used at the same position (e.g. all
   essays ending with a negative parallelism)

---

## 2. Tighten CLAUDE.md

### 2a. Add cross-essay consistency guidance to the Voice section

After "End with implications, not prescriptions" add something like:

- Vary the shape of essays. Not every piece should follow the same arc.
  Alternate between opening with observation, story, question, data, or
  direct claim.
- Avoid reusing concrete images across essays. "2am production incident" is
  vivid once. After that, find different details.
- If two essays reach the same conclusion, write the conclusion differently.
  Same thesis, different words.

### 2b. Add missing banned phrases

To "Structural Patterns to Avoid":
- "Here's a question" / "Here's what" (not just "Here's the thing")
- "deep dive" (corporate jargon that survived into casual use)
- "What this means for X" as a section header
- "The broader point" as a section header

### 2c. Update the repository structure

The repo structure in CLAUDE.md is stale (missing the two newer essays, the
reading section, images directory, etc.). Update it to reflect reality.

---

## 3. Deeper essay rewrites

The round-one fixes removed vocabulary and phrase-level tells. What remains
is the structural sameness. The essays would benefit from varying their shape.

Priority order:

### 3a. trust-not-capability.html (September 2025)

Most formulaic of the five. Every section follows "What X means in practice"
with a list. The argument is sound but the structure is predictable. Consider:
- Collapse the three "in practice" sections into a shorter, denser treatment
- Open differently (it currently opens with the thesis statement, same as ORE)
- The new conclusion is better but the essay still reads as "here's my
  framework, here are three pillars, here's what it means for leaders"

### 3b. ironies-of-automation.html (November 2025)

Strongest source material, second-strongest voice. This could be the best
essay in the collection with structural work:
- The opening is better now but could be more personal - what specifically
  was the engineer's reaction on reading the paper?
- "When the code handles money" section is the strongest writing on the site
  (specific, personal, concrete stakes). Could be expanded.
- "Designing for epistemic engagement" header is slightly academic

### 3c. observable-reversible-enforceable.html (February 2026)

The framework essay. By nature it's more structured, which is fine, but:
- Opens with the same "discussions start in the wrong place" framing as
  trust-not-capability
- Shares several paragraph shapes with trust-not-capability (they're
  essentially the same argument, expanded)
- Consider whether these two essays should remain separate or whether one
  supersedes the other

### 3d. ai-as-junior-engineer.html (August 2025) and the-suspicion-tax.html (January 2026)

These two are the strongest. The Suspicion Tax has the most voice. Junior
Engineer has the best actionable advice. Light touch only.

---

## 4. Suggested execution order

1. Upgrade the humaniser skill (1a-1d). This has the highest leverage because
   it improves every future writing session, not just the current essays.
2. Tighten CLAUDE.md (2a-2c). Quick changes that prevent recurrence.
3. Structural essay rewrites (3a-3c). Harder, higher-risk changes that
   require judgment about voice and argument. Do one at a time with review.

---

## 5. What I'd leave alone

- The Suspicion Tax. It's the best essay. Don't touch it.
- The About page. It reads human and serves its purpose.
- The landing page. Clean, tight, no tells.
