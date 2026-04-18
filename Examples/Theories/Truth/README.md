# ATN Example: Truth Theory

This example shows a minimal ATN specification for a theory with a single proposition.

In ATN, a theory is specified by the concepts and assertions that describe what must hold, rather than by procedural steps.

## Specification

```haskell
statement: Boolean

STATEMENT_HOLDS:
  statement
```

## Notes

- `statement` is a constant of type `Boolean`.
- `STATEMENT_HOLDS` asserts that the proposition defined by the theory is true.
- The example is intentionally minimal, showing a theory as a set of assertions about what holds.
