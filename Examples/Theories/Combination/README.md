# ATN Example: Combination Theory

This example shows a minimal ATN specification for a theory with an abstract function and algebraic laws.

In ATN, a theory may define abstract types, constants and functions, then constrain them with general assertions.

## Specification

```haskell
Element
combine: Element * Element -> Element
identity: Element

LEFT_IDENTITY:
  all x in Element:
    combine(identity, x) = x

RIGHT_IDENTITY:
  all x in Element:
    combine(x, identity) = x

COMBINATION_IS_ASSOCIATIVE:
  all x, y, z in Element:
    combine(combine(x, y), z) = combine(x, combine(y, z))
```

## Notes

- `Element` is the type whose instances are combined by the theory.
- `combine` is an abstract binary function over `Element`.
- `identity` is a distinguished instance of `Element` that leaves other elements unchanged when combined with them.
- `LEFT_IDENTITY` and `RIGHT_IDENTITY` state that `identity` behaves neutrally on both sides of the combination.
- `COMBINATION_IS_ASSOCIATIVE` states that the grouping of repeated combinations does not affect the result.
- The example is more expressive than `Ordering`, because it introduces both an abstract function and an abstract constant governed by quantified laws.
