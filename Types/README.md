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
