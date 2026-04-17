# ATN Example: Hello World Program

This example shows a minimal ATN specification for a program that outputs the classic greeting.

In ATN, the program is specified by its observable result, not by the implementation steps used to produce it.

## Specification

```haskell
output: String

OUTPUT_IS_HELLO_WORLD:
  output = "Hello, world!"
```

## Notes

- `output` is a constant of type `String`.
- `OUTPUT_IS_HELLO_WORLD` asserts that the program's output must be the string `"Hello, world!"`.
- The example specifies the required result of the program without prescribing how it prints or constructs the text.
