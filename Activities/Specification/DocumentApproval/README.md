# Document Approval Requirements

This document defines a small set of requirements for a document approval workflow.

## Scope

The workflow concerns a single document at a time.

## Requirements

- Every document has a title.
- Every document has a reviewed flag.
- Every document has an approved flag.
- A document may be approved only if it has been reviewed.
- A document may be reviewed only if its title is not empty.
- An approved document must also have a non-empty title.
