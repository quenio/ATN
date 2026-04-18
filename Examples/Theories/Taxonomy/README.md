# ATN Example: Taxonomy Theory

This example shows a minimal ATN specification for a theory with a subtype taxonomy.

In ATN, a theory may define abstract types and subtype relations, then constrain them with assertions about classification.

## Specification

```haskell
LivingBeing
Animal: LivingBeing
Plant: LivingBeing
Mammal: Animal
Bird: Animal

bat: Mammal
sparrow: Bird
oak: Plant

ALL_MAMMALS_ARE_ANIMALS:
  all x in Mammal:
    some y in Animal:
      x = y

ALL_BIRDS_ARE_LIVING_BEINGS:
  all x in Bird:
    some y in LivingBeing:
      x = y

NO_PLANT_IS_AN_ANIMAL:
  all x in Plant:
    not (some y in Animal:
      x = y)
```

## Notes

- `LivingBeing` is the most general type in the taxonomy.
- `Animal` and `Plant` are sub-types of `LivingBeing`.
- `Mammal` and `Bird` are sub-types of `Animal`.
- `bat`, `sparrow` and `oak` are constants classified within the taxonomy.
- `ALL_MAMMALS_ARE_ANIMALS` and `ALL_BIRDS_ARE_LIVING_BEINGS` illustrate inheritance through the subtype hierarchy.
- `NO_PLANT_IS_AN_ANIMAL` illustrates a classification constraint across distinct branches of the taxonomy.
- The example extends the theory progression by focusing on type hierarchy and classification instead of propositions, relations or algebraic structure.
