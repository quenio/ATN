# ATN Constants

A constant refers to a specific instance of a type.

## Specification

```haskell
-- Constants are defined in a context:
Constant
context: Constant -> Context

-- A constant has a single name but may also have aliases:
ConstantName :: /([a-z]([a-z][0-9]_)*)+/
name: Constant -> Constantame
aliases: Constant -> {ConstantName}
```
