# ATN Example: Approval Process With Roles

This example shows a minimal ATN specification for an approval process with explicit participants.

In ATN, the process is specified by the states, participants and assertions that describe its valid behavior, rather than by operational steps.

## Specification

```haskell
Person

requester: Person
reviewer: Person
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

REVIEWER_IS_NOT_THE_REQUESTER:
  not (reviewer = requester)
```

## Notes

- `Person` is the type of participants in the process.
- `requester` is the participant who initiates the process.
- `reviewer` is the participant responsible for reviewing it.
- `submitted`, `in_review`, `approved` and `rejected` describe the process state.
- `REVIEWER_IS_NOT_THE_REQUESTER` states a simple separation-of-duties rule.
- The example extends the review process by adding explicit roles while preserving the same staged constraints.
