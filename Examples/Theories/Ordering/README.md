# ATN Example: Ordering Theory

This example shows a minimal ATN specification for a theory with an abstract ordering relation over a type.

In ATN, a theory may define abstract types and relations, then constrain them with general assertions.

## Specification

```haskell
Element
precedes: Element * Element -> Boolean

NOTHING_PRECEDES_ITSELF:
  all x in Element:
    not precedes(x, x)

PRECEDENCE_IS_TRANSITIVE:
  all x, y, z in Element:
    precedes(x, y) and precedes(y, z) => precedes(x, z)

PRECEDENCE_IS_ASYMMETRIC:
  all x, y in Element:
    precedes(x, y) => not precedes(y, x)
```

## Notes

- `Element` is the type whose instances are ordered by the theory.
- `precedes` is a binary relation over `Element`.
- `NOTHING_PRECEDES_ITSELF` states that the ordering is irreflexive.
- `PRECEDENCE_IS_TRANSITIVE` states that the ordering composes across intermediate elements.
- `PRECEDENCE_IS_ASYMMETRIC` states that if one element precedes another, the reverse cannot also hold.
- The example is more abstract and general than `Truth` and `Implication`, because it specifies a relation over a type with quantified laws.
