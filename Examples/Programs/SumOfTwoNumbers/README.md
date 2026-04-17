# ATN Example: Sum of Two Numbers Program

This example shows a minimal ATN specification for a program that outputs the sum of two inputs.

In ATN, arithmetic behavior is specified by assertions about the expected result, rather than by an algorithm.

## Specification

```haskell
first_input: Natural
second_input: Natural
output: Natural

OUTPUT_IS_THE_SUM:
  output = first_input + second_input
```

## Notes

- `first_input` and `second_input` are constants of type `Natural` representing the program inputs.
- `output` is a constant of type `Natural` representing the program output.
- `OUTPUT_IS_THE_SUM` asserts that the output must be equal to the sum of the two inputs.
- The example specifies what result the program must produce, not how the addition is implemented.
