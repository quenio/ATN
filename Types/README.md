# ATN: Types

In ATN, a type is a [set](https://en.wikipedia.org/wiki/Set_(mathematics)) that integrates its elements (a.k.a. instances) into a named [concept](https://en.wikipedia.org/wiki/Concept).

## Type Declaration

A type is declared as one or more words, each with its first letter capitalized, all joined without spaces between them:


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

The super-type may have instances that are not instances of the sub-type. For example, not all instances of `Number` are instances of `RationalNumber`, as it is the case with the instances of `IrrationalNumber`.

## Type Alias

A type may have one or more aliases:

```haskell
World :: OuttermostEnvironment :: Environment :: Env
```

Within the current context, each alias may be used independently to refer to the same type.

Aliases are normally used for abbreviations or synonyms.

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

Note that, in the example above, the intersection of the constituent types is an empty set. That may not always be the case with a type union. In example below, the intersection of `IntegerNumber` and `RationalNumber` is not an empty set:

```haskell
SomeNumber :: IntegerNumber | RationalNumber
```

A type may also be defined by the union of multiple types. For example:

```haskell
Animal :: Mammal | Bird | Reptile | Amphibian | Fish | Invertebrate
```

## Function Type

A type may be define for functions:

```haskell
String :: Natural -> Character
```

In the example above, `String` is defined as the set of all functions that have `Natural` as domain and `Character` as the range.

Observe that function types allow ATN to refer to [functions as values](https://en.wikipedia.org/wiki/Higher-order_function). That is, as arguments and results in the application of other functions, such as [map](https://en.wikipedia.org/wiki/Map_(higher-order_function)), [filter](https://en.wikipedia.org/wiki/Filter_(higher-order_function)) and [fold](https://en.wikipedia.org/wiki/Fold_(higher-order_function)):

```haskell
StringMap :: String * [Natural] -> [Character]
```
