# Document Approval `./atn spec` Test

This folder contains a small end-to-end test for `./atn spec`.

It starts from a short natural-language requirements document for a document approval workflow and checks that `./atn spec` can generate a corresponding ATN specification.

## Files

- [`Requirements.md`](./Requirements.md): source requirements document
- [`Requirements.spec.md`](./Requirements.spec.md): generated ATN specification

## Activity Links

- [Specification](../../../Activities/Specification): refers to this folder as a small `./atn spec` example and test.

## Purpose

This test is meant to verify that `./atn spec` can:
- read a Markdown requirements document,
- extract its core requirements,
- and produce a faithful ATN specification in Markdown.
