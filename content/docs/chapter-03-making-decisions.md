---
title: "Making Decisions with Electricity: The Transistor"
weight: 3
aliases: ["/docs/chapter-02-making-decisions/"]
---

# 3. Making Decisions with Electricity: The Transistor

By the end of the last chapter we could write. A row of wires, each one merely on or off, could hold any number we liked — and any letter, any colour, anything at all we cared to make an agreement about.

And then we walked straight into the problem with writing something down: it just sits there. A row of wires holding thirteen holds thirteen forever. Nothing we have built can add to it, compare it, copy it, or react to it in any way at all. We have an alphabet, and we have a language, and we have nothing that can read.

So we left ourselves with a question: what if we want one wire to *react* to what other wires are doing?

To answer it, we need to look closer.

So far we've been picturing wires from a distance — long lines carrying a signal from one place to another, billions of them threaded across a chip. At that scale, a wire is just a wire. But a computer isn't only wires. It's wires that *meet*. Pick any two of them that need to come together and zoom in on the point where they join. Let's see what's actually there.

---

## Zooming In on the Junction

From far away, it looks like the two wires simply touch — signal flows in one, out the other, nothing to see. But that can't be the whole story. If every junction just passed signals straight through, the chip would be one giant tangle of wires all shouting at once, and nothing would ever *decide* anything.

So zoom in further, right to the gap where the wires almost meet. At this resolution, something new comes into view. The wires don't quite touch. Sitting in the gap between them is a tiny component — and whether the signal crosses from one wire to the other is up to it.

It's a switch.

Not the kind you flip with a finger. This switch has a third wire running to it, and *that* wire is what decides whether the gap is open or closed. When the third wire is on, the gap closes and the signal passes through. When it's off, the gap stays open and the signal is blocked.

That's the thing we were missing in the first two chapters. We saw wires carrying signals, and we learned to read those signals as numbers. We didn't yet see the switches sitting between them — the places where one wire gets to control another. They were there all along; we just hadn't looked closely enough.

This switch has a name. It's called a *transistor*.

---

## The Transistor: A Switch You Can Control with Electricity

Let's pin down exactly what we found in that gap.

A transistor has three connections. One wire brings electricity in. One wire lets it out the other side. And one wire — the control wire — decides whether the electricity is allowed to cross between them. When the control wire is on, the transistor conducts: electricity flows through. When the control wire is off, the transistor blocks: nothing gets through.

You already know most of this from ordinary switches. Flip a light switch and it either lets electricity through or blocks it. The only new idea is that this switch isn't flipped by a finger — it's flipped by another wire. Electricity controls electricity. That single twist is what lets one signal react to another.

This is the component that makes everything possible. Modern processors contain billions of them, each one smaller than a virus. But we don't need to worry about the physics of how a transistor is built. What matters is what it *does*: it lets one wire control whether another wire gets through.

It also helps to have a picture in mind for what we're about to do. Think of a transistor as a doorman standing in the gap between wires. A plain junction waves every signal through. A doorman applies a rule — "I'll only let this through under such-and-such conditions" — and the control wire is what tells him the conditions. One doorman alone enforces a simple rule. But line a few of them up, hand each one its own control wire, and the rules they can enforce together get surprisingly rich.

With that one trick, we can start building decision-making machines.

---

## Teaching Wires to Say "Both"

Let's build something. We have two input wires — call them A and B — and we want one output wire. The rule we want to enforce is:

> The output should only be on if *both* A *and* B are on.

If only A is on, the output stays off. If only B is on, the output stays off. The output only turns on when A and B are both on at the same time.

How do we build this?

Take two transistors and line them up in a chain. Wire A controls the first transistor, and wire B controls the second. Electricity has to pass through *both* transistors to reach the output. If either transistor is blocking — because its control wire is off — the electricity can't get through.

So:
- A off, B off → blocked at the first transistor → output off
- A on, B off → first transistor open, second blocked → output off
- A off, B on → blocked at the first transistor → output off
- A on, B on → both transistors open → electricity flows → output on

It only turns on when both inputs are on. Our doorman's rule is: "I need to see both of you." We've built that rule out of two transistors and a wire.

We'll give this its name in a moment. For now, just notice what happened: two simple switches, wired together carefully, enforce a logical rule.

---

## Teaching Wires to Say "Either"

Now let's try a different rule:

> The output should be on if *either* A *or* B is on (or both).

This time, instead of chaining transistors in a line, we put them side by side. Wire A controls one transistor, wire B controls the other. Both transistors connect to the same output. Electricity only needs to find one open path to reach the output.

- A off, B off → both transistors blocking → output off
- A on, B off → first transistor open → electricity gets through → output on
- A off, B on → second transistor open → electricity gets through → output on
- A on, B on → both open → electricity gets through → output on

The output is on whenever at least one input is on. The doorman's rule is now: "I'll let you in if either of you is on the list."

---

## Teaching a Wire to Flip

There's one more basic rule we need, and it's almost philosophically interesting.

> Whatever the input is, the output should be the *opposite*.

If the input is on, the output is off. If the input is off, the output is on. The wire doesn't pass the signal through — it inverts it.

We build this with a single transistor, but wired differently. Instead of the transistor sitting between the power source and the output, the transistor sits between the output and the ground (the off state). When the input is on, the transistor pulls the output down to off. When the input is off, the transistor stops pulling, and the output floats up to on.

It's a bit like a seesaw: when one side goes up, the other goes down.

---

## What We've Just Built

Let's take stock. Starting from nothing but the idea that a wire is on or off, and using transistors as electrically controlled switches, we've built three things:

1. A circuit that's only on when **both** inputs are on.
2. A circuit that's on when **either** input is on.
3. A circuit that **flips** its input to the opposite.

These three circuits are the complete toolkit. Every computation a computer ever performs — adding numbers, comparing values, storing data, running software — can be broken down into combinations of these three operations.

Now we can give them their names.

The "both" circuit is called an **AND gate**. The "either" circuit is called an **OR gate**. The "flip" circuit is called a **NOT gate** (also sometimes called an inverter).

Together, we call these structures **logic gates** — because they are gates that apply logical rules to electrical signals.

---

## The Surprising Power of NAND

Before we move on, there's one more gate worth meeting, because it turns out to be unexpectedly important.

What if we took our AND gate and attached a NOT gate to its output? The result would be a circuit that is *off* when both inputs are on, and *on* for every other combination. We call this a **NAND gate** (short for "Not AND").

Here's the remarkable thing: you can build *any* logic circuit in existence using only NAND gates. The AND, OR, and NOT gates we just built? All of them can be assembled from NAND gates alone. This means that if you can manufacture one type of component well, you can build the entire logical foundation of a computer from it. Real chip designers lean on this heavily.

The other compound gates — **NOR** (Not OR), **XOR** (on when inputs are *different*), and **XNOR** (on when inputs are the *same*) — are all combinations of the basics, each enforcing its own specific rule. You can think of them as words built from our three-letter alphabet of AND, OR, and NOT.

---

## Where We Are

We started this chapter by zooming in on the junction between two wires, and we found a switch sitting in the gap: the transistor, a switch controlled by electricity. We used it to build circuits that enforce logical rules. Those circuits are now our new building blocks. We don't need to think about transistors anymore; we can think in terms of gates.

But there's a problem we haven't solved yet. All of these gates are *stateless*. The moment you change the inputs, the output changes. The circuit has no memory of what it was doing a moment ago. It can't hold onto a value.

In the next chapter, we're going to ask: what happens if we connect a gate's output back to its own input? What happens when a circuit can hear itself?

That question leads somewhere strange and wonderful — and it's where memory begins.
