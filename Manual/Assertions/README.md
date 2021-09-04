# Assertions

In ATN, an assertion is a named expression that should always be true within the context where it is defined.

## Constant Assertions

The simplest assertion expression is the reference to a constant:

```haskell
true: Truth

TRUTH:
  true
```

## Congruent Assertions

```haskell
p: Truth
q: Truth

DE_MORGAN_THEOREM:
  not (p or q) <=> (not p) and (not q)
  not (p and q) <=> (not p) or (not q)
```

