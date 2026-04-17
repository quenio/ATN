# ATN Example: Smallest Program

This example shows a minimal ATN specification for a program.

In ATN, a program is specified by the types, constants and assertions that describe its observable behavior, rather than by implementation steps.

## Specification

```haskell
output: Boolean

OUTPUT_IS_TRUE:
  output
```

## Notes

- `output` is a constant of type `Boolean`.
- `OUTPUT_IS_TRUE` asserts that the program's output must evaluate to being true.
- The example specifies what the program must produce, not how it is implemented.
