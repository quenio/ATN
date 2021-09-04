# ATN Assertions

An assertion is a named [expression](https://en.wikipedia.org/wiki/Expression_(mathematics)) 
that should always evaluate to being true within the context where it is defined.

## Specification

```haskell
-- Assertions are defined in a context:
Assertion
context: Assertion -> Context

-- An assertion has a single name but may also have aliases:
AssertionName :: /([A-Z]([A-Z][0-9]_)+)+/
name: Assertion -> AssertionName
aliases: Assertion -> {AssertionName}

-- An assertion for which the expression is a constant:
ConstantAssertion: Assertion
expression: ConstantAssertion -> Constant
```
