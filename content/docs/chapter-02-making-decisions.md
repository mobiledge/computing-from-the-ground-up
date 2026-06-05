---
title: "Making Decisions with Electricity"
weight: 2
---

# Chapter 2: Making Decisions with Electricity

At the end of the last chapter, we landed on a single rule: a wire is either on (1) or off (0). That's the whole alphabet of a computer — two letters, nothing more.

But an alphabet on its own isn't useful. You need rules for combining letters into words. So the question we need to answer now is: how do we make wires interact with each other? How do we build something where the state of one wire depends on the state of others?

In other words — how do we make electricity make decisions?

---

## The Problem: Wires Don't Talk to Each Other

Take two wires. One is on. One is off. By themselves, they do nothing to each other. They can run side by side for metres without either one affecting the other. Wires, on their own, are passive. They carry a signal from one place to another, but they don't react to anything.

What we need is something in between — a component that sits between wires and says: *"I will look at what's coming in, and decide what goes out."*

Think of it like a doorman at a club. The doorman doesn't just wave everyone through (that would be a plain wire). He looks at who's arriving and applies a rule. Maybe his rule is: "both people in a group need ID." Or maybe: "let anyone through if at least one of them is on the guest list." The rule is what makes him useful. Without a rule, he's just standing in the way.

We need a doorman for electricity. Something that looks at incoming signals and applies a rule to decide the outgoing signal.

---

## The Transistor: A Switch You Can Control with Electricity

Here's where things get clever.

You already know what a light switch does. You flip it, and it either lets electricity through or blocks it. Simple. But a light switch needs a human finger to operate it — it can't respond to other electrical signals.

Now imagine a switch that you don't flip with your finger. Instead, you control it with another wire. When that control wire is on, the switch opens and lets electricity through. When the control wire is off, the switch closes and blocks it.

That's a *transistor*.

A transistor has three connections. One wire brings electricity in. One wire lets it out the other side. And one wire — the control wire — decides whether the electricity is allowed to pass. When the control wire is on, the transistor conducts: electricity flows through. When the control wire is off, the transistor blocks: nothing gets through.

It is, at its heart, just a switch. But it's a switch that electricity itself can flip.

This is the component that makes everything possible. Modern processors contain billions of them, each one smaller than a virus. But we don't need to worry about the physics of how a transistor is built. What matters is what it *does*: it lets one wire control whether another wire gets through.

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

We'll give this its name in a moment. For now, just notice what happened: two passive components, wired together carefully, enforce a logical rule.

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

We started this chapter with passive wires that couldn't interact. We introduced the transistor — a switch controlled by electricity — and used it to build circuits that enforce logical rules. Those circuits are now our new building blocks. We don't need to think about transistors anymore; we can think in terms of gates.

But there's a problem we haven't solved yet. All of these gates are *stateless*. The moment you change the inputs, the output changes. The circuit has no memory of what it was doing a moment ago. It can't hold onto a value.

In the next chapter, we're going to ask: what happens if we connect a gate's output back to its own input? What happens when a circuit can hear itself?

That question leads somewhere strange and wonderful — and it's where memory begins.
