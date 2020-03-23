# Review Questions

1. Why all learning problems are inverse problems, requiring unbounded exhaustive searches, thus ill-posed?

- Forward problem: give function $f$ and input $x$, compute $y$
- Learning problem is an inverse problem because we are given $x$ and $y$ and required to find $f$.

7. Why variable dependencies (interactions) could become an extremely difficult and even an impossible problem? Give philosophical, mathematical, physical, computational, and numerical examples for such a singularity.

Hilbert tenth problem is, per Wikipedia,

> the challenge to provide a general algorithm which, for any given Diophantine equation (a polynomial equation with integer coefficients and a finite number of unknowns), can decide whether the equation has a solution with all unknowns taking integer values.

The answer is no i.e. the problem of finding such solutions is undecidable. This has the implication that if a problem of variable dependencies can be expressed in a Diophantine equation, then the problem is undecidable, and *suggests* that a solution with low complexity (e.g. integer solution) is unlikely to be computed for more complex problems about variable dependencies (e.g. variable dependencies expressed as differential equations).

Examples:

- Philosophical: Godel's Incompleteness Theorems
- Mathematical: Fermat's Last Theorem, singularity in derivatives
- Physical: Three-body problem
- Computational: Indeterminacy in concurrent computing (Dijkstra proposed *concurrent computing* in 1965, not *indeterminacy* in concurrent computing)
- Numerical: Chaos

8. Why a Euclidean-based measure would be most favored but usually impossible to obtain for a real world issue?

Per Wikipedia,

> In mathematical analysis, a **measure** on a set is a systematic way to assign a number to each suitable subset of that set, intuitively interpreted as its size. In this sense, a measure is a generalization of the concepts of length, area, and volume.

It is unlikely that the word "measure" means the "size of sets" here in the question, taking into account the fact that words like "点积与测度 (Inner Product)" appears in the slides. Inner product in Euclidean space defines the famous Euclidean *metric* i.e. the straight-line distance between two points. Probably YB confuses "measure" with "metric", which "defines a distance between each pair of elements of a set" and is translated as "度量" or "距离函数".

It remains to be explained what the f\*\*k do "Euclidean-based metric" and "impossible to obtain" even mean. It could mean that the Euclidean metric or metrics in the Euclidean space fails to characterize the notion of distance in *some* feature space but succeeds in others, which doesn't say anything at all.

17. Using the Least Square as the objective function, we try to find the best set of parameters; what is the statistical justification for the Lease Square if the underlying distribution is Gaussian?

The weight vector obtained by least square is the same as that obtained from MLE assuming that the underlying distribution of error is Gaussian. See derivation on the slide.

22. Give a probabilistic interpretation for logistic regression, how is it related to the MLE-based generative methods from a Bayesian perspective?

Logistic regression makes the following assumption in probability (in the scenario of binary classification):
$$
    \Pr(Y = 1|X = x) = \frac{1}{1 + e^{-w^Tx}}
$$
and performs MLE to solve for $w$.

Generative methods model $p(y|x)$ with the Bayesian formula $p(x|y)p(y)$, while logistic regression directly imposes a distribution onto $p(y|x)$.

23. Can you provide a probabilistic comparison for liner and logistic regression?

Linear regression assumes that the error $\epsilon \sim \mathcal{N}(0, \sigma^2)$, where $\epsilon = Y - w^TX$, so
$$
    \Pr(Y = y|X = x) = \Pr(\epsilon = y - w^Tx) = \frac{1}{\sqrt{2\pi}\sigma}\exp(\frac{(y - w^Tx)^2}{2\sigma^2})
$$

Refer to the previous question for the probability assumption of logistic regression.

24. Why the log of odd would be something related to entropy and effective information?

The expression of the so-called log odd (should be log-likelihood) is exactly the entropy, saving for the minus sign.

52. Why local solution is the key difficulty in data mining, for more generalizable learning?

From YB's own words,

> ……局部解对于人工智能也好，数据挖掘也好，是个杀手。为什么呢？因为你有很多局部解的话，这个 y = f(x) 的话 x 和 y 的关系就会出现范围，你不同的局部解的话就会有不同的范围，你就必须考虑不同的 x 和不同的 y 要用不同的 f，你不能用一个函数去 extrapolate 所有可能的 x 和 y 的关系，所以你这个 local 解的话就会严重的约束你这个解的泛化能力。

YB seems to agree that each local solution of hyperparameters only makes correct predictions for a range of input, so to cover as much input as possible, we have to combine predictors with different sets of hyperparameters.
