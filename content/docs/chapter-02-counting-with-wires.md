---
title: "Counting with Wires: Binary"
weight: 2
---

# 2. Counting with Wires: Binary

At the end of the last chapter we made a promise. Eight wires, we said, give you 256 different combinations of on and off — and with enough wires you could represent every letter, every number, every colour, every pixel on a screen.

Time to make good on it. Because as things stand, it isn't quite true.

Eight wires do give us 256 patterns. But a pattern is not a number. If I show you eight wires reading *on-off-on-on-off-off-off-on*, you have learned nothing. It's a shape. Nothing about those wires says "this is one hundred and seventy-seven." Nothing about them says anything at all.

So before we build a single circuit, we have to solve a problem that has nothing to do with electricity: how does a pattern become a number?

The answer turns out to be something you have done every day since you were about five years old, without once noticing you were doing it.

---

## The Trick You Already Know

Look at this:

**437**

You read it instantly. Four hundred and thirty-seven. But stop and ask *why* it means that. There is nothing four-hundred-ish about the shape of the digit 4. It's a squiggle. So where does the meaning come from?

It comes from *where the squiggle sits*.

The 7 on the right is worth seven. The 3 beside it isn't worth three — it's worth thirty, because it sits one place to the left. The 4 isn't worth four, it's worth four hundred, because it sits two places to the left. Each position is worth ten times the position to its right:

- first position (rightmost): ones
- second position: tens
- third position: hundreds
- fourth position: thousands

So 437 is really (4 × 100) + (3 × 10) + (7 × 1). A digit's value depends entirely on the company it keeps.

Now here is the part nobody ever points out. Why ten? Why does each position jump by a factor of ten, rather than seven, or twelve, or two?

Because we have ten fingers.

That's the whole reason. We use ten symbols — 0 through 9 — because we learned to count on our hands, and when we ran out of hands we started a new column. There is no mathematical law underneath it. Somewhere far back, a species with ten fingers made a choice, and every one of us inherited it without being asked.

Which means the choice can be made differently. And it has to be, because a wire does not have ten fingers. It has two states.

---

## An Odometer With Two Positions

Picture the odometer in an old car: a row of little wheels behind a window, each printed with the digits 0 through 9. The rightmost wheel turns as you drive. When it passes 9 it rolls back to 0 and nudges the wheel to its left forward by one notch. When *that* wheel passes 9, it rolls over and nudges the next one along. Simple, mechanical, and it will count to hundreds of thousands using nothing but wheels that can each do only ten things.

Now build the same odometer, but give every wheel just **two** positions: 0 and 1.

Nothing else changes. Turn the right-hand wheel. When it runs out of symbols, roll it back to 0 and nudge its neighbour. That's the entire rule. Let's turn the crank and watch.

Start at nothing: `0`. Turn it once: `1`. Turn it again — but this wheel has no symbol after 1. So it rolls back to 0 and bumps the wheel beside it: `10`.

That is not "ten." It is the odometer telling us *I ran out of symbols once*. It means two.

Keep cranking:

- `0` → zero
- `1` → one
- `10` → two
- `11` → three
- `100` → four
- `101` → five
- `110` → six
- `111` → seven
- `1000` → eight

The wheels never do anything clever. They just roll over and nudge. And yet they count perfectly well, forever, with only two symbols to work with.

The place values follow the same logic they did in base ten, except each position is now worth *twice* the one to its right instead of ten times:

- first position: ones
- second position: twos
- third position: fours
- fourth position: eights
- fifth position: sixteens

So `1101` is (1 × 8) + (1 × 4) + (0 × 2) + (1 × 1) = **thirteen**.

Try it on the pattern from the top of this chapter. `10110001` is 128 + 32 + 16 + 1 = one hundred and seventy-seven. Which is exactly what I claimed it was, and now it isn't a claim.

This way of writing numbers is called **binary** — *bi* for two, because there are only ever two symbols.

And here is why it matters to us. Every wheel of that odometer is a thing with two positions. So is a wire. A row of eight wires *is* an eight-wheel binary odometer, and it can hold any number from 0 to 255.

That's the 256 from Chapter 1. Only now we know what the 256 things actually are.

---

## The Same Wires, A Different Agreement

Numbers are not the only thing we can decide a pattern means.

Take the eight wires reading `01000001`. Read as a number, that's 65.

But suppose we sit down and write out a table: 65 shall mean the letter A, 66 shall mean B, 67 shall mean C, and so on through every letter, digit and punctuation mark we care about. Nothing stops us. It is our table. Now those same eight wires spell **A**.

Or suppose we are driving a screen, and we agree that a byte will describe how bright the red part of a pixel should be — 0 for none, 255 for as much as the screen can give. Now those same eight wires are a **shade of dark red**.

Nothing changed in the wires. Not one electron behaved differently. The voltage is identical in all three cases. What changed is what we agreed to read.

And crucially, you cannot look at the wires and work out which agreement is in force. There is no test you can run, no meter you can attach. It is like looking at the letters C-A-T: nothing in the shape of those three marks tells you they mean a small furry animal. You only know because you already speak the language.

---

## The Second Ground Rule

Chapter 1 gave us the first rule of this book. Here is the second, and everything from here on leans on both:

> **A pattern of wires means whatever we have agreed it means. The wires do not know, and they do not care.**

Sit with that for a moment, because it is easy to nod at and hard to actually believe. There is no meaning hidden inside a computer. There is no layer, however deep you dig, where the electricity finally knows it is dealing with a photograph or a bank balance or a sentence. All the way down it is wires being on and off. Every scrap of meaning was put there by a person, in a table, by agreement.

This is also the loophole we will exploit later, and it is the strangest thing in the whole book. Since we can agree that a pattern means anything at all, at some point we are going to agree that a certain pattern means *"add the next two numbers together."* A number that is an instruction. That single move is what turns a pile of circuits into a machine that runs programs — and it is available to us only because meaning was never in the wires to begin with.

---

## Where We Are

We can now write things down. Any number, any letter, any colour — all of it, in nothing but rows of wires that are on and off.

And that is precisely the problem.

Because it just sits there. A row of wires holding thirteen holds thirteen, and goes on holding it, and does nothing else for the rest of time. Nothing we have built can add one to it, compare it against another row, copy it somewhere else, or react to it in any way whatsoever. We have invented writing, and we have no hands.

So in the next chapter we ask a question that sounds simple and turns out to be profound: what if we want one wire to *react* to what other wires are doing? What if we want a wire to turn on only when two other wires are both on? What if we want it to turn on when either one is on, but not both?

We'll build the answer from scratch — no prior knowledge required. And by the end of it, we'll have something that can make decisions.
