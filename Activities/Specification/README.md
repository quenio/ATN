# ATN Activities: Specification

Using ATN to specify required constraints, behaviors and invariants that serve as primary inputs to design and testing.

## [ModelContextProtocol](./ModelContextProtocol)

A larger `atn spec` example and test based on the Model Context Protocol specification, including a local source copy and a generated ATN version.

## Tests: `atn spec`

This folder includes two `atn spec` exercises:

- [`./DocumentApproval`](./DocumentApproval): a small end-to-end test based on a short natural-language requirements document for a document approval workflow.
- [`./ModelContextProtocol`](./ModelContextProtocol): a larger end-to-end example and stress test based on the Model Context Protocol specification.

Their purpose is to verify that the command can:
- read a Markdown requirements document,
- extract its core requirements,
- and produce a faithful ATN specification in Markdown.
