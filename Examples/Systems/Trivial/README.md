# ATN Example: Trivial System

This example shows a minimal ATN specification for a system.

In ATN, a system is specified by the states and assertions that describe its valid behavior, rather than by implementation details.

## Specification

```haskell
powered: Boolean
operational: Boolean

OPERATION_REQUIRES_POWER:
  operational => powered
```

## Notes

- `powered` indicates whether the system has power.
- `operational` indicates whether the system is operating.
- `OPERATION_REQUIRES_POWER` states that the system cannot operate unless it is powered.
- The example allows the system to be powered without operating, while constraining valid states.
