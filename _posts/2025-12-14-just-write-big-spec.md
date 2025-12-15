---
title: "Writing a Big Spec Fails. For now."
description: "Explaining why long specs miss the mark"
---
# Why "Big Spec” Fails

Anyone who’s tried to build something with AI knows the truth: **the code is often the easy part**.

The hard part is the translation. I mean the deeper translation: the messy, high-fidelity mental model we hold: the intent, the tradeoffs, the edge cases, the product shape, the constraints, the taste... the conversion of thought into code.

Today’s LLMs can operate on both sides of the equation:

- They understand language and can generate language.
- They understand code and can generate code.

But the crucial bridge between idea to **faithful** implementation is still mostly inside our heads and is shaped by hundreds of iterations we do on an idea before we choose to implement it as it is.

And that’s why long specs often die on the vine... for now.

---

## The Missing Artifact: Ideas Don’t Live Next to Code

Most training data the models see looks like this:

- Code repositories, often disconnected from the original “why”
- Docs, tickets, README files, and blog posts
- Examples, patterns, and textbooks

What they rarely see is the real creative pipeline:

- the half-formed idea
- the messy sketches
- the evolving intent
- the PRD, ADR, RFC
- the business pressure
- the “oh wait, that assumption is wrong” moment, discovery
- the repeated human corrections
- the random experiment
- the thousand micro-decisions

The ideas that become the code are not captured cleanly side-by-side with the final code. They happen in conversations, in someone’s head, on a whiteboard, in a wiki page, or in a Slack thread.

Documentation tries to approximate it, but documentation is always lossy.

So you can hand a model a “complete spec,” and it can still produce something technically correct while completely missing what you meant.

---

## “Add Two Numbers” Is Not the Point

Sure—an LLM can implement “add two numbers” in a hundred idiomatic ways.  
But the addition function *you* need might imply:

- precision rules, rounding, currency / locale constraints  
- overflow behavior, performance targets, vectorization  
- telemetry, error budgets, SLA expectations  
- future extension points that aren’t “requirements” yet

Textbook examples don’t contain that nuance, most public code doesn’t either.

So the model can generate **an** addition function—but not necessarily **your** addition function: the one aligned with your product’s value and constraints.

---

## This Isn’t Just a Software Problem

You can see the same gap in image generation as well: “Photo of a train” is not a universal request. A photographer will produce be able to iterate on a prompt for a more compelling train photo because they understand composition, lighting, lens choice, framing, mood, and audience taste. The model can output “a photo of a train,” but not reliably the one you meant or one with mass appeal.

**All this to say: The medium is not the idea.**

Models are good at producing media. Humans are still better at translating intention into media with mass appeal.

And mass appeal matters. Your output doesn’t just have to satisfy you and your brother's taste—it has to land for other people.

---

## What This Means for Software Engineers Right Now

### 1) Your Edge Is Still Translation, Not Syntax

LLMs commoditize syntax and patterns.  
They do **not** commoditize product judgment, tradeoffs, system shape, or the craft of turning intent into reality.

### 2) Big Specs Aren’t the Answer — Tight Feedback Loops Are

Instead of betting on a 30-page spec, you’ll get more progress from:

- iterative prototypes  
- quick “show me” slices  
- tests as executable intent  
- traceable decisions (ADRs, design notes)  
- structured constraints (“must be deterministic,” “must be auditable,” “must survive X”)  

### 3) The Winners Will Build Idea-Capture Systems, Not Just Models

The real breakthrough isn’t “smarter autocomplete.”

It’s instrumentation that captures intent:

- decisions made during implementation  
- corrections and *why* they happened  
- context around tradeoffs  
- relationships between requirements, code, and real-world outcomes  

The model needs the missing bridge—and the bridge is built from data that doesn’t exist in most workflows today.

---

## Closing Thought

LLMs can write code.  
They can write prose.  
They can mimic competence.

But the thing we mistake for “spec completeness”—the belief that language can fully represent intent—is exactly where projects fail.

The future isn’t:

> Humans write big specs and models write software.

The future is tighter loops, continuous intent capture, platform-hosted compute, and a truth that hasn’t changed:

**The most valuable human skill is translating messy ideas into real products that people actually want.**
