# ATN Example: Approval Process

This example shows a minimal ATN specification for a process that may remain pending or reach one of two possible decisions.

In ATN, the process is specified by the conditions that must hold for a valid state, rather than by operational steps.

## Specification

```haskell
submitted: Boolean
approved: Boolean
rejected: Boolean

PROCESS_CANNOT_BE_BOTH_APPROVED_AND_REJECTED:
  not (approved and rejected)

DECISION_REQUIRES_SUBMISSION:
  approved or rejected => submitted
```

## Notes

- `submitted` indicates that the process has been initiated.
- `approved` and `rejected` represent the two possible decisions.
- `PROCESS_CANNOT_BE_BOTH_APPROVED_AND_REJECTED` states that the decisions are mutually exclusive.
- `DECISION_REQUIRES_SUBMISSION` states that no approval or rejection may exist before submission.
- The example allows a submitted process to remain pending, while still constraining which combinations of states are valid.
