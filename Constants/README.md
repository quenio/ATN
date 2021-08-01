# ATN: Constants

In ATN, a constant refers to a specific instance of a type.

## Constant Declaration

A constant is declared as one or more words, each one in lower-case, all joined with an underscore character between them. For example:


```haskell
total_amount -- The total amount to be paid.
```

Just writing the name of the constant is enough to have it known in the current context. No definition is required.

## Type Definition

A constant may have its type defined as follows:

```haskell
total: Amount
```

That means the constant named `total` refers to an instance of `Amount`, whichever it is.

Any definition allowed in [types](../Types) may also be used to define the type of a constant. Some examples shown below:

```haskell
album: {Photo}
indices: [Natural]
center: Latitude * Longitude
```

## Function Definition
