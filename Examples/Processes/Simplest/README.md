# ATN Example: Simplest Process

This example shows a minimal ATN specification for a process.

In ATN, a process is specified by the states, conditions and assertions that describe its required behavior, rather than by operational details.

## Specification

```haskell
completed: Boolean

PROCESS_IS_COMPLETED:
  completed
```

## Notes

- `completed` is a constant of type `Boolean`.
- `PROCESS_IS_COMPLETED` asserts that the process must be completed.
- The example specifies the required outcome of the process, not how the process is carried out.
