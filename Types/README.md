# ATN: Types

In ATN, a type is a [set](https://en.wikipedia.org/wiki/Set_(mathematics)) that integrates its elements (a.k.a. instances) into a named [concept](https://en.wikipedia.org/wiki/Concept).

## Type Declaration

A type is declared as one or more words, each with its first letter capitalized, all joined without spaces between them:


```haskell
RationalNumber
```

As shown above, just the name of the type is suffcient to have it known in the current context. No definition is required.

## Type Hierarchy

A type can be declared as a sub-type of a super-type:

```haskell
RationalNumber: Number
```

That means all instances of the sub-type are also instances of the super-type.

The super-type may have instances that are not instances of the sub-type.

## Type Alias

A type may have one or more aliases:

```haskell
World :: OuttermostEnvironment :: Environment :: Env
```

Within the current context, each alias may be used independently to refer to the same type.

Aliases are normally used for abbreviations or synonyms.

## Type Product

A type may be defined as a product of two other types:

```haskell
Point :: Latitude * Longitude
```

A product type is a [binary relation](https://en.wikipedia.org/wiki/Binary_relation) between two types. Its instances are all the pairwise combinations of all the instances of the constituent types.

Normally, instances are represented as pairs, such as `(1, 2)`, where `1` is an instance of `Latitude` and `2` is an instance of `Longitude`.

A type may be also defined by the product of multiple types. For example:

```haskell
Box :: Height * Width * Length
```

In which case, the instances would be tuples of the 3 constituent types, such as `(1, 2, 3)`.
