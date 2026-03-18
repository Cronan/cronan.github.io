# Context and source material for "672 bytes"

This file contains everything needed to write the essay without web access. Read fully before writing.

---

## 1. The repository

**Repo:** https://github.com/Cronan/zx81-chess
**Live demo:** https://cronan.github.io/zx81-chess/play/
**Contributors:** Ivan Cronyn (Cronan) and Claude
**Language breakdown:** Python 38.9%, HTML 23.8%, Assembly 17.7%, JavaScript 15.6%, BASIC 3.7%
**Commits:** 74
**License:** MIT

---

## 2. The byte budget (from README)

```
Component        Bytes   What it does
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Board Data         64    The 8x8 board (1 byte/square)
Variables           7    Cursor, move coords, best move
Lookup Tables      38    Piece chars, values, directions
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Display            85    Draw board to screen
Input              90    Read player moves from keyboard
Move Logic        100    Execute moves, pawn promotion
AI Engine         250    Generate moves, evaluate, choose
Game Loop          38    Main loop, win/lose detection
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
TOTAL             672    Every byte accounted for
```

The AI engine alone (scanning pieces, generating legal moves, evaluating captures, picking the best) takes 37% of the entire program. Display and input together are another 26%. That leaves 250 bytes for everything else.

---

## 3. The two-line BASIC program

```
1 REM ... (672 bytes of machine code hiding in here)
2 RAND USR 16514
```

The BASIC interpreter skips over anything after REM. The Z80 processor doesn't know what REM is. `RAND USR 16514` jumps straight into the machine code bytes stored inside the REM statement. The entire program hides inside a BASIC comment.

---

## 4. Technical details

**Target machine:** Sinclair ZX81 / Timex Sinclair 1000
**CPU:** Zilog Z80A @ 3.25 MHz
**RAM required:** 1024 bytes (1K), no expansion
**Code size:** 672 bytes of Z80 machine code
**Language:** Z80A assembly, hand-assembled
**Board storage:** 64 bytes inside the REM statement
**AI depth:** 1-ply with material evaluation
**Display:** Direct display-file manipulation
**Input:** Algebraic notation (E2E4 style)

### Key space-saving tricks

**Board lives in the REM statement** — The 64-byte chess board is stored at the start of the machine code area, inside the BASIC REM statement. The board data IS the REM content. The ZX81 skips past REM, but `USR 16514` jumps into it as executable code. Dual-purpose memory.

**Direction bitmask for sliding pieces** — Bishop, Rook and Queen all use the same 8-direction loop. A bitmask ($A5 for Bishop, $5A for Rook, $FF for Queen) selects which directions are active. One loop, three piece types. Saves approximately 30 bytes (4.5% of the entire program).

**No separate initialisation data** — The starting position is generated algorithmically. The back rank pattern (R N B Q K B N R) is stored once (8 bytes) and reused for both White and Black.

**Pawn promotion in 12 bytes** — Checks if a pawn reached the far rank, replaces it with a Queen. No choice of piece.

**King capture = checkmate** — Full check/checkmate detection would cost ~80+ bytes. Instead, the game ends when someone captures the King. You can technically move into check. The computer won't stop you, but it will take your King.

### What was cut (and the cost in bytes)

- Castling: ~40 bytes
- En passant: ~30 bytes
- Check detection: ~80+ bytes
- Opening book: not remotely feasible
- Input validation: minimal (the player can cheat)
- Promotion choice: 0 bytes saved by forcing Queen

### The AI

1-ply search with material evaluation:
1. Scans all 64 squares for its own (Black) pieces
2. Generates all legal-ish moves for each piece using direction tables
3. Scores each move: captures score the value of the captured piece
4. Picks the highest-scoring move
5. Plays it

Known weaknesses: no look-ahead, slight queenside bias (scans a-h, keeps first equally-scored move), no opening theory, doesn't understand check, no castling/en passant/promotion choice.

Strengths: always captures undefended pieces, prefers Queens over Pawns, makes reasonable developing moves when no captures available.

---

## 5. The personal story (from MY-STORY.md)

### Christmas 1981, Durban, South Africa

Ivan was twelve. His dad gave him two Christmas presents: a Sinclair ZX81 (imported from overseas, not easy in South Africa in those days) and "Programming the Z80" by Rodnay Zaks (Sybex, 624 pages, third revised edition). His dad wasn't a computer person, but figured out what his kid needed and went and found it.

The ZX81 was smaller than school textbooks. Lighter than a pencil case. A flat membrane keyboard. 1K of RAM. They hooked it up to the family telly with an RF lead, channel 36. Black and white, slightly wobbly. Christmas in the southern hemisphere, thirty-something degrees outside.

### Learning alone

Ivan learned to program entirely on his own. No school computer club, no friends with ZX81s, no local user group. Durban in 1982, not Silicon Valley. No Internet. Just the machine, the Zaks book, and whatever copies of "Your Computer" or "Sinclair User" made it to South Africa.

He also had access to an IBM reference manual from his dad's work (probably a System/360 principles of operation manual), which gave him a more formal treatment of two's complement arithmetic.

### No assembler — hand-assembly process

There was no assembler (none he could afford, and nothing that would run in 1K). The process:

1. Write Z80 mnemonics on paper (LD A, 42 / CP 64 / JR NZ, -4)
2. Look up each instruction in the opcode table at the back of the Zaks book
3. Write down the hex bytes (3E 2A / FE 40 / 20 FC)
4. Calculate jump offsets by hand (counting bytes forward or backward)
5. Double-check everything
6. Type the bytes into the ZX81 using POKE commands from the keyboard
7. Type RAND USR 16514

One wrong byte and the ZX81 would crash. Hard crash. Garbage characters on screen. Back to the K cursor, having lost everything not saved to tape. Saving to tape meant a portable cassette recorder, hoping the heads were clean and the volume was right.

### The chess project

Not a weekend project. Took the better part of two years (mid-1982 to some point in 1983). Ivan started at twelve, got it working at fourteen.

He filled an exercise book with the design: diagrams, tables, calculations. Board representation (bits 0-2 for piece type, bit 3 for colour). Direction offsets. Memory budgets scribbled in margins.

The bitmask breakthrough happened on the bus home from school. One bitmask to share a sliding loop between Bishop, Rook and Queen. Saved ~30 bytes. He nearly shouted.

### The moment it worked

Board display came first (weeks of work, had ranks upside down for an embarrassing time). Player input next. The thinking routine was the mountain — 250 bytes of move generation and evaluation.

Typed in the last POKE. Saved to tape. Saved to tape again on a different cassette. Then RAND USR 16514. The board appeared. Played E2 E4. The computer thought for two seconds and played D7 D5 (the Scandinavian Defence — it could recapture with the queen if the pawn was taken).

His dad played it. Didn't really understand what he was looking at — inverse video characters on a wobbly TV — but when the computer took his bishop, he said "It's actually quite good, isn't it?"

### The tape

The game stayed on a C15 cassette labelled "CHESS" in biro. Went into a shoebox, under the bed, through a house move, out of Durban. Found years later, tape degraded beyond loading. The exercise book with the hex dump was gone too (may have ended up levelling a table in his first flat in Johannesburg).

### The rewrite

The repository is NOT the original 1982-83 code. That code is lost. This is a complete rewrite done as an adult, in the spirit of the teenager. Some tricks are ones genuinely used back then. Others benefit from decades of hindsight. Ivan is explicit about this: "it would be dishonest to pretend otherwise."

The constraints are real. 1K of RAM. The Z80A instruction set. Every byte earned.

---

## 6. Author background

Ivan Cronyn. Head of Solutions Technology at Man Group, London. Twenty-seven years in London finance: Barclays Capital, Merrill Lynch, GLG Partners, Brevan Howard, Man Group. Languages: C++, C#, Python. Coding since 1981 (ZX81, Durban, South Africa).

His thesis on AI: "Trust, not capability" — AI is a force multiplier only if systems are designed to absorb mistakes cheaply.

Personal site: cronyn.co.uk

---

## 7. Published writing — voice samples

These are excerpts from Ivan's published essays. Study the voice, sentence rhythm, and structure. The new essay must feel like it belongs alongside these.

### From "Trust, not capability" (July 2025)

> I keep seeing the same sequence play out.
>
> Someone introduces an AI coding tool. Output goes up. Code review starts taking longer, because reviewers can't tell whether the person submitting the PR actually understands what they're submitting.
>
> [...]
>
> That's a trust problem, not a capability problem. And trust doesn't scale with model accuracy.
>
> [...]
>
> The teams I see making real progress with AI aren't the ones with the best models. They're the ones where the engineering infrastructure was already strong enough that new code — from any source — gets challenged and verified rather than taken on faith.
>
> [...]
>
> Before asking "which AI tools should we use?", ask "what happens when they get it wrong?" If you don't like the answer, that's your backlog.

### From "Observable, reversible, enforceable" (December 2025)

> After twenty-seven years of building financial systems, I've noticed that production readiness always comes down to the same three things, whether the work is done by humans, traditional automation, or AI.
>
> Can you see what happened and why? Can you undo a bad outcome cheaply? Are the constraints checked by machines rather than remembered by people?
>
> Observable, reversible, enforceable. Miss any one and you're running a demo that happens to touch real data.
>
> [...]
>
> AI systems are stochastic. The same input can produce different outputs. The model that worked fine yesterday might hallucinate today. Your test suite covers the cases you anticipated, not the ones you didn't.
>
> [...]
>
> The advantage won't go to whoever adopts fastest. It will go to the teams whose systems were already built to absorb errors from any source — human or machine — without drama.

### Voice characteristics observed in published work

- Opens with observation or a grounded statement, never a grand claim
- Uses "I" only when personal experience is the evidence
- Paragraphs are short. Many are 2-3 sentences.
- Short declarative sentences after longer ones for rhythm
- Concrete specifics (twenty-seven years, SM&CR, 5pm on month-end)
- States claims plainly: "That's a trust problem, not a capability problem."
- Ends sections and pieces with implications, not exhortations
- No hedging, no meta-commentary, no enthusiasm markers
- British spellings throughout

---

## 8. The existing writing catalogue (for context on positioning)

1. "The 25 ways AI overwrites your voice" — February 2026
2. "Compromised Witnesses" — February 2026
3. "Observable, reversible, enforceable" — December 2025
4. "The Suspicion Tax" — November 2025
5. "Bainbridge's Ironies of Automation, forty years on" — August 2025
6. "Trust, not capability" — July 2025
7. "Building engineers in the age of AI" — May 2025

The new essay would be the newest piece (March 2026). It's the first piece on the site with a substantial personal/autobiographical element. That's a deliberate choice — the personal material earns its place by serving the argument about constraints. It should not feel like a departure from the site's tone.

---

## 9. Historical/technical context (for reference, not inclusion)

The ZX81 was released by Sinclair Research in March 1981. Membrane keyboard, 1K RAM, TV for a monitor. Brought computing to hundreds of thousands of people who couldn't afford a "real" computer. The machine was available in the UK and exported internationally; importing one to South Africa in 1981 was non-trivial.

"Programming the Z80" by Rodnay Zaks (Sybex, 3rd revised edition, 624 pages) was the standard Z80 reference. Not ZX81-specific — covered the Z80 processor for any platform. Built concepts methodically from binary arithmetic through to interrupt handling.

1K ZX Chess by David Horne (1982, published in Your Computer magazine February 1983) was a separate, well-known chess program for the ZX81 at 672 bytes. Ivan's project was independent and personal. **Do not mention David Horne or 1K ZX Chess in the essay** — this is about Ivan's own work, not a commentary on Horne's.
