# ATN Example: Sorting Program

This example shows a minimal ATN specification for a program that sorts a sequence of natural numbers.

In ATN, sorting is specified by the properties of the resulting sequence, rather than by implementation steps such as swaps or loops.

## Specification

```haskell
sort: [Natural] -> [Natural]
length: [Natural] -> Natural
count: [Natural] * Natural -> Natural
input: [Natural]
output: [Natural]

OUTPUT_IS_THE_SORTED_SEQUENCE:
  output = sort(input)

SORT_OF_EMPTY_SEQUENCE:
  sort([]) = []

SORT_OF_SINGLETON_SEQUENCE:
  all n in Natural:
    sort([n]) = [n]

SORT_PRESERVES_LENGTH:
  all values in [Natural]:
    length(sort(values)) = length(values)

SORT_PRESERVES_ELEMENT_COUNTS:
  all values in [Natural]:
    all x, n in Natural:
      count(sort(values), x) = n <=> count(values, x) = n

SORT_OUTPUT_IS_NONDECREASING:
  all values in [Natural]:
    all i in Natural:
      i + 1 < length(values) => sort(values)(i) <= sort(values)(i + 1)
```

## Notes

- `input` is a constant of type `[Natural]` representing the program input.
- `output` is a constant of type `[Natural]` representing the program output.
- `sort` is an abstract function over sequences of natural numbers.
- `length` and `count` are used to express general properties of sorting.
- `SORT_PRESERVES_ELEMENT_COUNTS` states that, for every value and every possible multiplicity, sorting preserves whether that value occurs that many times, including repeated values.
- `SORT_OUTPUT_IS_NONDECREASING` states that the resulting sequence is ordered from smaller to greater values.
- The example specifies what a sorting program must produce, not which sorting algorithm it uses.
