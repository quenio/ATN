# ATN Example: Approval Process

This example shows a minimal ATN specification for a process that reaches one of two possible decisions.

In ATN, the process is specified by the conditions that must hold for a valid outcome, rather than by operational steps.

## Specification

```haskell
submitted: Boolean
approved: Boolean
rejected: Boolean

PROCESS_WAS_SUBMITTED:
  submitted

PROCESS_CANNOT_BE_BOTH_APPROVED_AND_REJECTED:
  not (approved and rejected)

PROCESS_MUST_REACH_A_DECISION:
  approved or rejected
```

## Notes

- `submitted` indicates that the process has been initiated.
- `approved` and `rejected` represent the two possible decisions.
- `PROCESS_CANNOT_BE_BOTH_APPROVED_AND_REJECTED` states that the decisions are mutually exclusive.
- `PROCESS_MUST_REACH_A_DECISION` states that the process must end in one of the two decisions.
- The example specifies the valid outcomes of the process, not the operational workflow that leads to them.
