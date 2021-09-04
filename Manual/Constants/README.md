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

Since ATN allows the definition of [function types](https://en.wikipedia.org/wiki/Function_type), as seen in [types](../Types), a constant can be used to define a specific [function](https://en.wikipedia.org/wiki/Function_(mathematics)), as shown in the following example:

```haskell
sum: [Amount] -> Amount
```

Observe that, in the example above, and generally in ATN specifications, the function definition does _not_ describe how the function should be implemented. [Assertions](../Assertions), however, allow ATN to specify the expected behavior of a function in different situations. 

An assertion that specifies the behavior of `sum` can be as simple as:

```haskell
SUM_OF_3_NUMBERS: sum([1, 2, 3]) = 6
```

Normally though, they involve variables and are more generic, such as:

```haskell
SUM_OF_3_NUMBERS: 
  all a, b, c in Number:
    sum([a, b, c]) = a + b + c
```

See more about assertions [here](../Assertions).

## Attribute / Association Definition

Just as [function types](https://en.wikipedia.org/wiki/Function_type) in ATN allow the definition of functions, they can also be used to define [attributes](https://en.wikipedia.org/wiki/Attribute_(computing)) and [associations](https://en.wikipedia.org/wiki/Association_(object-oriented_programming)) between types:

```haskell
first_name: Employee -> String
last_name: Employee -> String

employees: Employer -> {Employee}
employer: Employee -> Employer
```

In the example above, the `Employee` has two attributes (`first_name` and `last_name`), which are defined by declaring `Employee` as the domain of the function type and `String` as its codomain.

Similarly, the one-to-many association `employees` is defined from `Employer` to `Employee`, where `Employer` is the domain of the function type, and the `{Employee}` set type is its codomain. 

Alternatively, a one-to-one association from `Employee` to `Employer` is defined by `employer`. The main difference between the definitions of those two associations is the use of a set type as the codomain of the `employees` one-to-many association.
