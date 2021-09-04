# ATN Constants

A constant refers to a specific instance of a type.

## Specification

```haskell
-- Constants are defined in a context:
Constant
context: Constant -> Context

-- A constant has a single name but may also have aliases:
ConstantName :: /([a-z]([a-z][0-9]_)*)+/
name: Constant -> ConstantName
aliases: Constant -> {ConstantName}

-- A constant refers to an instance of a type:
type: Constant -> Type
```
