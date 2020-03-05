# Review Questions

1. Why all learning problems are inverse problems, requiring unbounded exhaustive searches, thus ill-posed?

- Forward problem: give function $f$ and input $x$, compute $y$
- Learning problem is an inverse problem because we are given $x$ and $y$ and required to find $f$.

6. Why variable dependencies (interactions) could become an extremely difficult and even an impossible problem? Give philosophical, mathematical, physical, computational, and numerical examples for such a singularity.

Hilbert tenth problem is, per Wikipedia,

> the challenge to provide a general algorithm which, for any given Diophantine equation (a polynomial equation with integer coefficients and a finite number of unknowns), can decide whether the equation has a solution with all unknowns taking integer values.

The answer is no i.e. the problem of finding such solutions is undecidable. This has the implication that if a problem of variable dependencies can be expressed in a Diophantine equation, then the problem is undecidable, and *suggests* that a solution with low complexity (e.g. integer solution) is unlikely to be computed for more complex problems about variable dependencies (e.g. variable dependencies expressed as differential equations).

Examples:

- Philosophical: Godel's Incompleteness Theorems
- Mathematical: Fermat's Last Theorem, singularity in derivatives
- Physical: Three-body problem
- Computational: Indeterminacy in concurrent computing (Dijkstra proposed *concurrent computing* in 1965, not *indeterminacy* in concurrent computing)
- Numerical: Chaos
