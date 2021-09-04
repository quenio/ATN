# Assertions

In ATN, an assertion is a named expression that should always be true within the context where it is defined.

## Constant Assertions

The simplest assertion expression is the reference to a constant:

```haskell
true: Boolean

TRUTH:
  true
```

## Negative Assertions

The simplest logic operator in an assertion is the negation:

```haskell
false: Boolean

TRUTH:
  not false
```

## Conjunct Assertion

The assertion composed of two other assertions by a conjunction:

```haskell
true: Boolean
false: Boolean

TRUTH:
  true and not false
```

## Congruent Assertions

```haskell
p: Boolean
q: Boolean

DE_MORGAN_THEOREM:
  not (p or q) <=> (not p) and (not q)
  not (p and q) <=> (not p) or (not q)
```

