# ATN Example: Reverse String Program

This example shows a minimal ATN specification for a program that outputs the reverse of a string.

In ATN, the program is specified by the relation between input and output, together with assertions that characterize the abstract reverse operation.

## Specification

```haskell
reverse: String -> String
input: String
output: String

OUTPUT_IS_THE_REVERSE:
  output = reverse(input)

REVERSING_TWICE_YIELDS_THE_ORIGINAL:
  all text in String:
    reverse(reverse(text)) = text

REVERSE_OF_HELLO:
  reverse("Hello") = "olleH"
```

## Notes

- `input` is a constant of type `String` representing the program input.
- `output` is a constant of type `String` representing the program output.
- `reverse` is an abstract function over strings.
- `OUTPUT_IS_THE_REVERSE` specifies the observable behavior of the program.
- The additional assertions help characterize what the reverse operation means.
