# ATN Example: Max of Two Numbers Program

This example shows a minimal ATN specification for a program that outputs the greater of two natural numbers.

In ATN, the program is specified by assertions about the required result, without prescribing how the comparison is implemented.

## Specification

```haskell
max: Natural * Natural -> Natural
first_input: Natural
second_input: Natural
output: Natural

OUTPUT_IS_THE_MAXIMUM:
  output = max(first_input, second_input)

MAXIMUM_IS_NEVER_SMALLER_THAN_FIRST:
  all a, b in Natural:
    max(a, b) >= a

MAXIMUM_IS_NEVER_SMALLER_THAN_SECOND:
  all a, b in Natural:
    max(a, b) >= b

MAXIMUM_IS_ONE_OF_THE_ARGUMENTS:
  all a, b in Natural:
    max(a, b) = a or max(a, b) = b
```

## Notes

- `first_input` and `second_input` are constants of type `Natural` representing the program inputs.
- `output` is a constant of type `Natural` representing the program output.
- `max` is specified as the function that returns one of its arguments and is never smaller than either of them.
- `OUTPUT_IS_THE_MAXIMUM` connects the program output to that abstract specification.
