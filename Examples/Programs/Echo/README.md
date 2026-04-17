# ATN Example: Echo Program

This example shows a minimal ATN specification for a program that returns its input unchanged.

In ATN, the relationship between the program input and output is specified declaratively, without describing implementation steps.

## Specification

```haskell
input: String
output: String

OUTPUT_EQUALS_INPUT:
  output = input
```

## Notes

- `input` is a constant of type `String` representing the program input.
- `output` is a constant of type `String` representing the program output.
- `OUTPUT_EQUALS_INPUT` asserts that the output must be equal to the input.
- The example specifies the observable behavior of the program, not how the program copies the text.
