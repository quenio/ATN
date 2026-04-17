# ATN Example: Reverse String Program

This example shows a minimal ATN specification for a program that outputs the reverse of a string.

In ATN, the program is specified by the relation between input and output, together with assertions that characterize the abstract reverse operation.

## Specification

```haskell
reverse: String -> String
length: String -> Natural
input: String
output: String

OUTPUT_IS_THE_REVERSE:
  output = reverse(input)

REVERSING_TWICE_YIELDS_THE_ORIGINAL:
  all text in String:
    reverse(reverse(text)) = text

REVERSE_PRESERVES_LENGTH:
  all text in String:
    length(reverse(text)) = length(text)

REVERSE_MIRRORS_CHARACTER_POSITIONS:
  all text in String:
    all i in Natural:
      i < length(text) => reverse(text)(i) = text(length(text) - i - 1)
```

## Notes

- `input` is a constant of type `String` representing the program input.
- `output` is a constant of type `String` representing the program output.
- `reverse` is an abstract function over strings.
- `length` is used to express general properties of string reversal.
- `OUTPUT_IS_THE_REVERSE` specifies the observable behavior of the program.
- The additional assertions characterize reversal in general terms, instead of relying on a single concrete example.
