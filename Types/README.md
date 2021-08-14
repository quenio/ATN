# ATN: Types

In ATN, a type is a [set](https://en.wikipedia.org/wiki/Set_(mathematics)) that integrates its elements (a.k.a. instances) into a named [concept](https://en.wikipedia.org/wiki/Concept).

## Type Declaration

A type is declared as one or more words, each with its first letter capitalized, all joined without spaces between them. For example:


```haskell
RationalNumber -- A number that can be expressed as the quotient of two integers.
```

Just writing the name of the type is enough to have it known in the current context. No definition is required.

## Type Hierarchy

A type can be declared as a sub-type of a super-type:

```haskell
RationalNumber: Number
IrrationalNumber: Number
```

That means all instances of the sub-type are also instances of the super-type. In the example above, all instances of `RationalNumber` are also instances of `Number`.

The super-type may have instances that are not instances of the sub-type. For example, not all instances of `Number` are instances of `RationalNumber`. That is also the case with the instances of `IrrationalNumber`.

## Type Alias

A type may have one or more aliases:

```haskell
World :: OuttermostEnvironment :: Environment :: Env
```

Within the current context, each alias may be used independently to refer to the same type.

Aliases are normally used for abbreviations or synonyms.

## Set Type

A type may be defined for instances that are themselves a set containing other elements, which are in turn instances of another type:

```haskell
Album :: {Photo}
```

In the example above, an instance of `Album` is a set containing instances of `Photo`.

A set type, as defined in ATN, is equivalent to the concept of [powerset](https://en.wikipedia.org/wiki/Power_set) in set theory, where the instances of the set type are subsets containing elements of the enclosed type.

## Sequence Type

A type may be defined for instances that are sequences containing (possibly repeated) elements of another type:

```haskell
String :: [Character]
```

In the example above, instances of `String` are sequences of `Character` instances.

Notice that a sequence type contains as its instances the sequences of any length, including infinite sequences.

## Product Type

A type may be defined as a product of two other types:

```haskell
Point :: Latitude * Longitude
```

A product type is a [binary relation](https://en.wikipedia.org/wiki/Binary_relation) between two types. Its instances are all the pairwise combinations of all the instances of the constituent types.

Its instances are represented as pairs, such as `(1, 2)`, where `1` is an instance of `Latitude` and `2` is an instance of `Longitude`.

A type may also be defined by the product of multiple types. For example:

```haskell
Box :: Height * Width * Length
```

In which case, the instances would be tuples composed by the instances of the constituent types, such as `(1, 2, 3)`.

## Union Type

A type may be defined as the union of two other types:

```haskell
RealNumber :: RationalNumber | IrrationalNumber
```

That means all instances of the union-type are also an instance of one of the constituent types. For example, an instance of `RealNumber` is either an instance of `RationalNumber` or an instance of `IrrationalNumber`.

Note that, in the example above, the intersection of the constituent types is an empty set. Sometimes, that may *not* be the case with a union type. In example below, the intersection of `IntegerNumber` and `RationalNumber` is not an empty set:

```haskell
SomeNumber :: IntegerNumber | RationalNumber
```

A type may also be defined by the union of multiple types. For example:

```haskell
Animal :: Mammal | Bird | Reptile | Amphibian | Fish | Invertebrate
```

## Function Type

A type may be defined for functions. For example:

```haskell
String :: Natural -> Character
```

In the example above, `String` is defined as the set of all functions that have `Natural` as the [domain](https://en.wikipedia.org/wiki/Domain_of_a_function) and `Character` as the [codomain](https://en.wikipedia.org/wiki/Codomain).

Observe that function types allow ATN specifications to use [functions as values](https://en.wikipedia.org/wiki/Higher-order_function). That is, as arguments and results in the application of other functions, such as [map](https://en.wikipedia.org/wiki/Map_(higher-order_function)), [filter](https://en.wikipedia.org/wiki/Filter_(higher-order_function)) and [fold](https://en.wikipedia.org/wiki/Fold_(higher-order_function)). For example:

```haskell
StringMap :: String * [Natural] -> String
```

Above, the instance of `String` can be used as a function that will allow a `StringMap` instance to map a sequence of natural numbers to another `String`. (This is the basic principle of cryptography.)

In ATN, sequence types are equivalent to function types having `Natural` as the domain:

```haskell
String :: [Character] :: Natural -> Character
```

Above, both definitions of `String` are equivalent. That is only true because `Character` is the enclosing type of the sequence type and also the codomain of the function type.
