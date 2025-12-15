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
- the thousand micro-decisions that shape a product

At work, the ideas that become the code are not captured cleanly side-by-side with the final code. They happen in conversations, in someone’s head, on a whiteboard, in a wiki page, or in a Slack thread.

Documentation tries to approximate it, but documentation is always lossy.

So you can hand a model a “complete spec,” and it can still produce something technically correct while completely missing what you meant.

