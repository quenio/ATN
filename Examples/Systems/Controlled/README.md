# ATN Example: Controlled System

This example shows a minimal ATN specification for a system with an intermediate enablement state before operation.

In ATN, a system is specified by the states and assertions that describe its valid behavior, rather than by implementation details.

## Specification

```haskell
powered: Boolean
enabled: Boolean
operational: Boolean

ENABLEMENT_REQUIRES_POWER:
  enabled => powered

OPERATION_REQUIRES_ENABLEMENT:
  operational => enabled
```

## Notes

- `powered` indicates whether the system has power.
- `enabled` indicates whether the system has been enabled for operation.
- `operational` indicates whether the system is operating.
- `ENABLEMENT_REQUIRES_POWER` states that the system cannot be enabled unless it is powered.
- `OPERATION_REQUIRES_ENABLEMENT` states that the system cannot operate unless it has been enabled.
- The example allows the system to be powered without being enabled, and enabled without operating, while constraining valid states.
