# ATN Example: Review Process

This example shows a minimal ATN specification for a process with an intermediate review stage before a decision is reached.

In ATN, the process is specified by the conditions that must hold for a valid state, rather than by operational steps.

## Specification

```haskell
submitted: Boolean
in_review: Boolean
approved: Boolean
rejected: Boolean

PROCESS_CANNOT_BE_BOTH_APPROVED_AND_REJECTED:
  not (approved and rejected)

REVIEW_REQUIRES_SUBMISSION:
  in_review => submitted

DECISION_REQUIRES_REVIEW:
  approved or rejected => in_review
```

## Notes

- `submitted` indicates that the process has been initiated.
- `in_review` indicates that the process has entered its review stage.
- `approved` and `rejected` represent the two possible decisions.
- `PROCESS_CANNOT_BE_BOTH_APPROVED_AND_REJECTED` states that the decisions are mutually exclusive.
- `REVIEW_REQUIRES_SUBMISSION` states that review cannot happen before submission.
- `DECISION_REQUIRES_REVIEW` states that approval or rejection can only happen after review.
- The example allows the process to remain submitted or in review without yet reaching a decision.
