# ATN Activities: Specification

Using ATN to specify required constraints, behaviors and invariants.

## [ModelContextProtocol](./ModelContextProtocol)

A local copy of the Model Context Protocol specification and its generated ATN version.

## Test: `atn spec`

This folder includes a small test under [`./DocumentApproval`](./DocumentApproval) to exercise `atn spec`.

The test starts from a short natural-language requirements document for a document approval workflow and uses `atn spec` to generate a corresponding ATN specification.

Its purpose is to verify that the command can:
- read a Markdown requirements document,
- extract its core requirements,
- and produce a faithful ATN specification in Markdown.
