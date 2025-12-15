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

But the crucial bridge between idea to faithful** implementation is still mostly inside our heads and is shaped by hundreds of iterations we do on an idea before we choose to implement it as it is.

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

**The medium is not the idea.**

Models are good at producing media. Humans are still better at translating intention into media with mass appeal.

And mass appeal matters. Your output doesn’t just have to satisfy you and your brother's taste—it has to land for other people.

---

## Why Invest Half a Trillion into Infrastructure?

So how does OpenAI, Anthropic, Google, Microsoft, et. al. intend to fix this?

Real-use-case feedback loops.

- humans correcting outputs  
- rejecting wrong interpretations  
- steering models toward what they actually meant  

That feedback is effectively reinforcement learning at scale—shaping the translation layer over time.

But that takes:

- huge infrastructure  
- enormous storage and compute  
- continuous data capture and analysis  
- lots of inference capacity  

And they can’t foot the bill for unlimited free usage forever.

So we’re seeing the platform play emerge:

- build more infrastructure  
- improve capability  
- monetize access to the heavy lifting  

---

## The Coming “Personal App” Era — and Why It Won’t Run Locally (for Most People)

We’re already seeing a shift:

More people are signing up for developer programs to build personal tools, personal automations, personal “apps that do exactly what I want.”

That expands.

Over time, the friction to “make an app” drops until it feels normal—not just for professional developers, but for regular people.

But here’s the catch: the **app that produces apps** is compute-hungry.

Most phones won’t run that locally because:

- inference is expensive  
- memory needs grow quickly  
- energy / battery constraints are real  
- truly capable local-first devices will be premium (thousands of dollars)  

So the likely mainstream path looks like this:

1. You own a normal-priced device.  
2. You pay a platform provider (Apple, Google, Autodesk, etc.) for hosted inference, storage, orchestration, and personalized services.  
3. Your “personal apps” live and run on their infrastructure, served on demand.  

That becomes a new revenue stream—and a new layer of lock-in:

Not just app stores, but **model stores, agent runtimes, personal workflows, and hosted intelligence**.

---

## We Are in the VHS Era of AI, Not the Streaming Era

The leap is still huge—like moving from handwritten letters to email, or from VHS to downloading video.

It’s mind-blowing compared to what we had.

But it’s also crude:

- expensive  
- inconsistent  
- not universally accessible  
- often frustrating for non-experts  

It’s early-stage technology wearing late-stage hype.

Professionals extract value because they already know how to build. For them, AI is another power tool—one they can correct, shape, and integrate into an existing craft.

For most people, the translation layer is still missing. So “just tell the AI what you want” doesn’t reliably yield something polished, safe, correct, and broadly useful.

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
