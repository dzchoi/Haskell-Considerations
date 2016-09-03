# Haskell-Insights

### Why function application is left-associative
- In a sense, Haskell is similar to the FORTH language: all 'words' are executed in the order of presence (left-to-right), but they may be:
  - just a value (if it stands alone) or
  - a single-argument function (if it is accompanied by another word) that consumes(takes) the next word as its argument unevaluated.

- If a right-associative function application is needed, we can use the lowest precedence and left-binding operator, `$`, which can be well regarded as a left parenthesis and we can also assume the corresponding right parenthesis being all the way down at the end of the line. So,
  - `f a b` is interpreted as `(f a) b`, and
  - `f $ a b` is interpreted as `f (a b)`.

### Haskell vs Lambda Calculus
- Lambda calculus is not a practical language, although it can be simulated under a computer. Lambda calculus is more abstract than Haskell. Everything in lambda calculus is defined as a function (e.g., the number `0` is defined to be the identity function.)
- That said, there is some heritage in Haskell from lambda caculus, the lazy evaluation. Function application is a matter of parameters substitution rather than evaluation. So, functions in Haskell can be thought as smart macros as in typical imperative languages. That means a function call in Haskell does not trigger the function evaluation and it is just a macro-expansion. That is why the evaluation in Haskell is called `lazy` as opposed to the strict evaluation.
