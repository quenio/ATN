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

-- Any type belongs to a hierarchy:
super_types: Type -> {Type}
sub_types: Type -> {Type}

-- A type for sets containing elements of another type:
SetType: Type
element_type: SetType -> Type

-- A type for sequences containing (possibly repeated) elements of another type:
SeqType: Type
element_type: SeqType -> Type

-- A type defined as a (ordered) product of other types:
ProductType: Type
product_types: ProductType -> [Type]

-- A type defined as the union of other types:
UnionType: Type
union_types: UnionType -> {Type}
```
