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
album: {Photo} -- This album is simply a set of photos.
indices: [Natural] -- The indices are a sequence of natural numbers.
city_center: Latitude * Longitude -- The city's center is a pair consisting of a latitude and a longitude.
```

## Function Definition

Since ATN allows the definition of [function types](https://en.wikipedia.org/wiki/Function_type), as seen in [types](../Types), a constant can be used to define a specific function, as shown in the following example:

```haskell
sum: [Amount] -> Amount
```

Observe that, in the example above, and generally in ATN specifications, the function definition does _not_ describe how the function should be implemented. [Assertions](../Assertions), however, allow ATN to specify the expected behavior of a function in different situations.
