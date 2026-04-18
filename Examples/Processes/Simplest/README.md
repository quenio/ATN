# ATN Example: Simplest Process

This example shows a minimal ATN specification for a process.

In ATN, a process is specified by the states, conditions and assertions that describe its required behavior, rather than by operational details.

## Specification

```haskell
submitted: Boolean
completed: Boolean

PROCESS_IS_COMPLETED:
  completed

COMPLETION_REQUIRES_SUBMISSION:
  completed => submitted
```

## Notes

- `submitted` indicates that the process has been initiated.
- `completed` is a constant of type `Boolean`.
- `PROCESS_IS_COMPLETED` asserts that the process must be completed.
- `COMPLETION_REQUIRES_SUBMISSION` states that the process cannot be completed before it has been submitted.
- The example specifies the required outcome of the process, not how the process is carried out.
