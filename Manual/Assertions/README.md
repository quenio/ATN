# Assertions

In ATN, an assertion is a named expression that should always be true within the context where it is defined.

## Constants

The simplest assertion expression is the reference to a boolean constant:

```haskell
true: Boolean

TRUTH:
  true
```

## Negations

The simplest logic operator in an assertion is the negation operator (`not`):

```haskell
false: Boolean

TRUTH:
  not false
```

## Conjunctions

An assertion composed of two other assertions by the conjunction operator (`and`):

```haskell
true: Boolean
false: Boolean

TRUTH:
  true
  not false
  true and not false
  not false and true
```

## Disjunctions

An assertion composed of two other assertions by the disjunction operator (`or`):

```haskell
true: Boolean
false: Boolean

TRUTH:
  true
  not false
  true or false
  false or true
```

## Implications

An assertion composed of two other assertions by the implication operator (`=>`):

```haskell
true: Boolean
false: Boolean

TRUTH:
  true
  not false
  false => false
  false => true
  true => true
  not (true => false)
```

## Equivalences

An assertion composed of two other assertions by the equivalence operator (`<=>`):

```haskell
true: Boolean
false: Boolean

TRUTH:
  true
  not false
  true <=> true
  false <=> false
  not (true <=> false)
  not (false <=> true)

p: Boolean
q: Boolean

CONTRAPOSITION:
  (p => q) <=> (not q => not p)

DE_MORGAN_THEOREM:
  not (p or q) <=> (not p) and (not q)
  not (p and q) <=> (not p) or (not q)
  
IMPLICATION_EQUIVALENCE:
  (p => q) <=> (not p) or q
```

## Universal Quantifications

An assertion prefixed by the [universal quantifier](https://en.wikipedia.org/wiki/Universal_quantification) (`all var in Type`):

```haskell
EXCLUDED_MIDDLE_LAW:
  all p in Boolean:
    p or not p
```

## Existential Quantifications

An assertion prefixed by the [existential quantifier](https://en.wikipedia.org/wiki/Existential_quantification) (`exists var in Type`):

```haskell
TRUTH:
  any p in Boolean:
    p
```
