# ATN Types

Types are [sets](https://en.wikipedia.org/wiki/Set_(mathematics)) that integrate its elements (a.k.a. instances) into a named [concept](https://en.wikipedia.org/wiki/Concept).

## References

- [Contexts](../Contexts)

## Specification

```haskell
TypeName :: /([A-Z]([a-z][0-9])*)+/

Type

context: Type -> Context
name: Type -> TypeName
aliases: Type -> {TypeName}
super_types: {Type}
sub_types: {Type}
```
