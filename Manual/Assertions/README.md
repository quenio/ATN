# Assertions

In ATN, an assertion is a named expression that should always be true within the context where it is defined.

## Constant Assertions

The simplest assertion expression is the reference to a boolean constant:

```haskell
true: Boolean

TRUTH:
  true
```

## Negation Assertions

The simplest logic operator in an assertion is the negation operator (`not`):

```haskell
false: Boolean

TRUTH:
  not false
```

## Conjunction Assertions

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

## Disjunction Assertions

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

## Implication Assertions

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

## Equivalence Assertions

An assertion composed of two other assertions by the equivalence operator (`<=>`):

```haskell
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

