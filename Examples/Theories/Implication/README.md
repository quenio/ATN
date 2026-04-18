# ATN Example: Implication Theory

This example shows a minimal ATN specification for a theory with a logical dependency between two propositions.

In ATN, a theory can relate propositions by assertions that constrain how their truth values may combine.

## Specification

```haskell
premise: Boolean
conclusion: Boolean

PREMISE_IMPLIES_CONCLUSION:
  premise => conclusion
```

## Notes

- `premise` and `conclusion` are constants of type `Boolean`.
- `PREMISE_IMPLIES_CONCLUSION` asserts that whenever the premise is true, the conclusion must also be true.
- The example is more expressive than `Truth` because it specifies a dependency between propositions rather than a single fact.
