# Why “Just Write a Big Spec” Fails With Today’s LLMs — and What Actually Works

Large language models can write software. They can also write documentation. And yet, anyone who’s tried to build something real with them knows the uncomfortable truth: **the code is often the easy part**.

The hard part is the translation.

Not “translate English to Python.”  
Not “turn requirements into a REST API.”

I mean the deeper translation: the messy, high-fidelity mental model a senior engineer holds—the intent, the tradeoffs, the edge cases, the product shape, the constraints, the taste—and the conversion of that into something shippable.

Today’s LLMs can operate on both sides of the equation:

- They understand language and can generate language.
- They understand code and can generate code.

But the crucial bridge between **idea → faithful implementation** is still mostly inside our heads.

And that’s why long specs often die on the vine.

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
- the business pressure  
- the “oh wait, that assumption is wrong” moment  
- the repeated human corrections  
- the thousand micro-decisions that shape a product  

In real engineering work, the ideas that become the code are not captured cleanly side-by-side with the final code. They happen in conversations, in someone’s head, on a whiteboard, in a notebook, or in a Slack thread that disappears into history.

Documentation tries to approximate it—but documentation is always lossy.

So you can hand a model a “complete spec,” and it can still produce something technically correct while completely missing what you meant.

---

## Why a Long Spec Can Still Produce Nothing

A long spec assumes that if you describe enough, the system can reconstruct the intended product.

But **description fidelity isn’t reality fidelity**.

There’s a classic compression problem here:
