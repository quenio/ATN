# ATN Example: Protected System

This example shows a minimal ATN specification for a system with enablement, operation and fault protection constraints.

In ATN, a system is specified by the states and assertions that describe its valid behavior, rather than by implementation details.

## Specification

```haskell
powered: Boolean
enabled: Boolean
operational: Boolean
faulted: Boolean

ENABLEMENT_REQUIRES_POWER:
  enabled => powered

OPERATION_REQUIRES_ENABLEMENT:
  operational => enabled

ENABLEMENT_REQUIRES_NO_FAULT:
  enabled => not faulted
```

## Notes

- `powered` indicates whether the system has power.
- `enabled` indicates whether the system has been enabled for operation.
- `operational` indicates whether the system is operating.
- `faulted` indicates whether the system is in a fault condition.
- `ENABLEMENT_REQUIRES_POWER` states that the system cannot be enabled unless it is powered.
- `OPERATION_REQUIRES_ENABLEMENT` states that the system cannot operate unless it has been enabled.
- `ENABLEMENT_REQUIRES_NO_FAULT` states that the system cannot even be enabled while faulted.
- The example adds a stronger protection constraint on top of the controlled system, making it slightly more expressive while remaining simple.
