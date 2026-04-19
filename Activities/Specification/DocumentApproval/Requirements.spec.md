# Document Approval Requirements Specification

This document converts the natural-language requirements in `Activities/Specification/DocumentApproval/Requirements.md` into an ATN specification.

## Extracted Requirements

- The workflow concerns a single document at a time.
- Every document has a title.
- Every document has a reviewed flag.
- Every document has an approved flag.
- A document may be approved only if it has been reviewed.
- A document may be reviewed only if its title is not empty.
- An approved document must also have a non-empty title.

## Assumptions

- Because the stated scope is a single document at a time, the specification models one document state directly with constants rather than a collection of documents.
- A non-empty title is represented by `not (title = "")`.

## Specification

```haskell
title: String
reviewed: Boolean
approved: Boolean

APPROVAL_REQUIRES_REVIEW:
  approved => reviewed

REVIEW_REQUIRES_NON_EMPTY_TITLE:
  reviewed => not (title = "")

APPROVED_DOCUMENT_REQUIRES_NON_EMPTY_TITLE:
  approved => not (title = "")
```

## Notes

- `title` specifies that the document has a title value of type `String`.
- `reviewed` specifies the document's reviewed flag.
- `approved` specifies the document's approved flag.
- `APPROVAL_REQUIRES_REVIEW` states that approval is only valid after review.
- `REVIEW_REQUIRES_NON_EMPTY_TITLE` states that a reviewed document must have a non-empty title.
- `APPROVED_DOCUMENT_REQUIRES_NON_EMPTY_TITLE` states that an approved document must also have a non-empty title.
- The specification constrains valid document states without prescribing an implementation workflow.
