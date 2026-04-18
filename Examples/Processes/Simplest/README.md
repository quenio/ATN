# ATN Example: Simplest Process

This example shows a minimal ATN specification for a process.

In ATN, a process is specified by the states, conditions and assertions that describe its valid behavior, rather than by operational details.

## Specification

```haskell
submitted: Boolean
completed: Boolean

COMPLETION_REQUIRES_SUBMISSION:
  completed => submitted
```

## Notes

- `submitted` indicates that the process has been initiated.
- `completed` indicates whether the process has been completed.
- `COMPLETION_REQUIRES_SUBMISSION` states that the process cannot be completed before it has been submitted.
- The example allows the process to be either completed or not completed, while still constraining valid states.
