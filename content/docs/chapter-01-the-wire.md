---
title: "The Wire: Electricity as Information"
weight: 1
---

# Chapter 1: The Wire — Electricity as Information

Let's start with the most honest possible description of a computer.

It is a machine made of wires. Billions of them, impossibly small, etched into a sliver of silicon you could hold between your fingers. And at any given moment, each one of those wires is doing exactly one of two things: it either has electricity flowing through it, or it doesn't.

That's it. That is the foundation everything else is built on.

You might be waiting for the catch — the asterisk, the "but of course it's more complicated than that." There isn't one. Not yet. Before we can talk about processors, memory, software, or any of the other things that make a computer feel like magic, we need to sit with this single idea long enough for it to feel real.

A wire is on, or it is off.

---

## What We Mean by "Electricity"

Imagine a garden hose. When you turn the tap on, water rushes through it. When you turn the tap off, it stops. The hose itself doesn't change — it's the same hose either way. What changes is whether something is flowing through it.

A wire works the same way. Inside every wire is a sea of tiny particles called electrons. They're always there, packed into the metal, but they aren't doing much on their own. Connect the wire to a battery or a power source, and something changes: those electrons start moving. They flow from one end to the other, like water through the hose. We call this flow of electrons *electricity*.

When electrons are flowing, we say the wire is *on*. When they're not, we say it's *off*.

Now here's the key question: how do we tell the difference? How does a machine know whether a wire is on or off?

The answer is *voltage*. Think of voltage as the pressure behind the flow. A wire with electricity running through it has a higher pressure — a higher voltage — than a wire sitting idle. We can measure this difference. If the voltage is high, we call it *on*. If it's low (or zero), we call it *off*.

You don't need to know the exact numbers. What matters is that this is a yes-or-no question. There's no in-between that the computer cares about. High voltage, or low voltage. On, or off.

---

## The Power of Two States

At first glance, "on or off" sounds laughably limited. How could anything useful come out of something so simple?

Think about a light switch. It has two positions. On its own, it can only tell you one thing: whether the lights are on. That's not very expressive. But now imagine a whole house full of light switches — say, 8 of them in a row. Suddenly you have 256 possible combinations of on and off. Add 8 more switches, and you have over 65,000 combinations. Add a few more rows and you can represent every letter, every number, every colour, every pixel on your screen.

The richness doesn't come from any single wire being clever. It comes from combining many simple wires together. A wire that is on or off is like a single letter of an alphabet. One letter isn't a language. But with enough letters, you can write anything.

This is the core insight that everything in this book rests on. We don't need wires to do anything complicated. We just need a lot of them, and a way to combine them.

---

## Why Electricity? Why Not Something Else?

It's a fair question. You could, in principle, build a computer out of water pipes, or gears, or pneumatic tubes. People have tried versions of all of these. But electricity has two properties that make it uniquely suited for the job.

The first is *speed*. Electrical signals travel through wires at a significant fraction of the speed of light. A signal can cross a modern processor — a chip smaller than your thumbnail — billions of times per second. No mechanical system comes close.

The second is *scale*. With modern manufacturing, we can etch billions of tiny switches onto a piece of silicon the size of a fingernail. Each switch is a few nanometres across — smaller than a virus. You simply cannot build mechanical parts that small.

So electricity isn't a magical choice. It's just the best tool we have found for the job: it's fast, it scales down to almost nothing, and it gives us a clean yes-or-no signal to work with.

---

## Setting the Ground Rule

Before we move on to the next chapter, let's make the one rule of this book explicit, because every single thing that follows will depend on it:

> **A wire can be in exactly one of two states: on (1) or off (0).**

That's the bedrock. We'll call the two states **1** and **0** — not because those numbers mean "one" and "zero" in the normal arithmetic sense, but simply because we need a shorthand for "on" and "off."

In the next chapter, we're going to ask a question that sounds simple but turns out to be profound: what if we want one wire to *react* to what other wires are doing? What if we want a wire to turn on only when two other wires are both on? What if we want it to turn on when either one is on, but not both?

We'll build the answer from scratch — no prior knowledge required. And by the end of it, we'll have something that can make decisions.
