# ATN Example: Factorial Program

This example shows a minimal ATN specification for a program that outputs the factorial of a natural number.

In ATN, the factorial is specified by mathematical properties, while the program output is specified as the value of that function for the given input.

## Specification

```haskell
factorial: Natural -> Natural
input: Natural
output: Natural

FACTORIAL_OF_ZERO:
  factorial(0) = 1

FACTORIAL_OF_SUCCESSOR:
  all n in Natural:
    factorial(n + 1) = (n + 1) * factorial(n)

FACTORIAL_OF_ONE:
  factorial(1) = 1

OUTPUT_IS_THE_FACTORIAL:
  output = factorial(input)
```

## Notes

- `input` is a constant of type `Natural` representing the program input.
- `output` is a constant of type `Natural` representing the program output.
- `factorial` is specified recursively by its base case and successor case, with `factorial(1)` stated explicitly as well.
- `OUTPUT_IS_THE_FACTORIAL` connects the observable output of the program to the mathematical definition.
