---
title: "What is categorical probability theory?"
description: A short introduction to the ideas behind my earlier dissertation work.
categories: [research, category-theory]
---

Categorical probability theory applies tools from category theory to probability theory. The hope is that abstraction buys us something concrete: diagrammatic languages, reusable proofs, and a cleaner foundation for probabilistic programming.

My master’s dissertation, *Applications of Monoidal Topology to Categorical Probability Theory*, used category theory to translate ideas from topology into probability. The translation produces objects that can look unusual from the perspective of standard probability, but which recur in quasi-Bayesianism, infra-Bayesianism, and imprecise probability.

One useful starting point is the familiar identity

\[
P(A \mid B) = \frac{P(A \cap B)}{P(B)}, \qquad P(B) > 0.
\]

Categorical probability asks which parts of probabilistic reasoning depend on the particular representation above, and which follow from deeper compositional structure.

I’ll use this blog to work through those ideas more carefully. Some familiarity with monads—and preferably Eilenberg–Moore algebras—will help, but I’ll try to state prerequisites as they arise.

