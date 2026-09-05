# Computing from the Ground Up
## Full Outline — One Book, Three Parts

One continuous argument in 27 chapters, at roughly 1,500 words each — about
40,000 words. Chapters are numbered continuously across all three parts, so
that a callback in chapter 27 can reach back to chapter 2 without ceremony.
The parts are structural, not separate volumes: none of them stands alone.

Detailed chapter-level bullets for Part One live in `table-of-contents.md`.

---

## The Rules Behind the Titles

Every chapter title is `pain or action : the name you earned`. The left side
is the problem the reader can feel before they have any vocabulary for it;
the right side is the term they are handed only after they've built the thing.
The format is the "earn your vocabulary" rule in miniature.

It is also a test. If the right-hand side can't be filled in, the chapter
probably doesn't earn a name, and may not be a chapter.

---

## The Ground Rules

Each part rests on one rule the reader can hold in their head:

- **Part One** — A wire is on (1) or off (0). And: a pattern of wires means
  whatever we have agreed it means; the wires do not know and do not care.
- **Part Two** — A number can be a command. Every chapter is that same
  loophole applied at a larger scale, and nothing new is ever added.
- **Part Three** — The machine has no senses. Everything it will ever know of
  the world arrives as a number at an address, and everything it will ever
  say leaves the same way.

---

## Part One — The Machine
*a wire to a working CPU*

1. Electricity as Information: **The Wire**
2. Counting with Wires: **Binary**
3. Making Decisions with Electricity: **The Transistor**
4. Teaching a Wire to Remember: **The Flip-Flop**
5. Scaling Memory Up: **RAM**
6. Teaching Wires to Calculate: **The ALU**
7. Directing Traffic: **The Control Unit**
8. Putting It Together: **The CPU**

---

## Part Two — The Commands
*a number can be a command*

9. A Number That Means "Do Something": **The Instruction**
10. A List of Commands: **The Program**
11. A Command That Points at Another: **The Jump**
12. A Command That Runs a Whole List: **The Function**
13. Commands About Commands: **The Assembler**
14. A Program That Writes Programs: **The Compiler**
15. Your Program Is Not Running: **The Interrupt**
16. A Program That Runs Programs: **The Operating System**
17. Putting It Together: **Software**

Chapter 17 hands the reader the word *software* for the first time, after
nine chapters of building the thing it names.

---

## Part Three — The Senses
*the machine reaches the world*

18. Addresses That Aren't Memory: **The Device**
19. Turning a Press into a Number: **The Scan Code**
20. Keeping What Arrives Too Fast: **The Buffer**
21. Painting with Memory: **The Frame Buffer**
22. Colour as Agreement: **The Pixel**
23. Drawing the Letter A: **The Glyph**
24. Making It Move: **The Refresh**
25. Sharing One Screen: **The Compositor**
26. Memory That Outlives the Power: **The Drive**
27. Putting It Together: **The Interface**

Chapter 22 deliberately echoes chapter 1's title, *Electricity as
Information*. Same move, twenty-one chapters later: a physical thing standing
in for something it isn't, by agreement.

---

## The Two Bookends

The book opens on a handful of sand and closes on the other half of that
thought.

**Chapter 8** (end of Part One) carries the sand callback:

> Look back at what we built. A switch became a gate, gates became memory,
> memory and arithmetic became a machine that runs programs. And all of it —
> every wire, every switch — is etched into a sliver of refined sand.

**Chapter 27** (end of the book) closes the frame:

> The machine has still never seen a letter, or a colour, or you. It received
> numbers and it emitted numbers. Every bit of meaning in the whole journey
> happened in your head, under an agreement you made back in chapter 2 and
> never once thought about again.

Each part ends on a *Putting It Together* chapter, and the three payoffs
escalate: a CPU, then software, then the interface.

---

## Open Questions

- **"There Is No Such Thing as a File."** Currently folded into chapter 16.
  Strong enough to stand alone, which would make Part Two ten chapters and
  shift everything after it. Decide when writing chapter 16, not before.
- **Sound.** A chapter on what a sound is — a number sixty thousand times a
  second — would parallel chapter 22 nicely and is cheap to write. Optional.
- **Networks are deliberately out of scope.** The moment a second machine
  enters, the ground rule inverts (the wire is unreliable and neither end can
  know the other's state). That is a different book, not a fourth part.

---

## A Note on Publishing This

This is a planning document, not a publishing one. Nineteen unwritten chapter
titles on the live site read as vapour and make the project feel further from
done than it is. Publish Part One's eight chapters, mark the unwritten ones as
coming, and mention Parts Two and Three in a single line without listing them.
