# ATN Types

Types are [sets](https://en.wikipedia.org/wiki/Set_(mathematics)) that integrate its elements (a.k.a. instances) into a named [concept](https://en.wikipedia.org/wiki/Concept).

## References

- [Contexts](../Contexts)

## Specification

```haskell
-- Types are defined in a context:
Type
context: Type -> Context

-- A type has a single name but may also have aliases:
TypeName :: /([A-Z]([a-z][0-9])*)+/
name: Type -> TypeName
aliases: Type -> {TypeName}

-- Any type belongs to a hierachy:
super_types: {Type}
sub_types: {Type}
```