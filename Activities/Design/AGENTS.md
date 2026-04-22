# AGENTS

Instructions for work under [`Activities/Design`](./README.md).

These instructions are especially important when using `./atn design` to translate an ATN specification into an ATN design.

## Goal of translation

The goal is to produce an ATN design that preserves the input specification while refining it into implementable structure.

The design should identify:
- architectural elements,
- interfaces and interaction points,
- component responsibilities,
- allocation of specified behavior and constraints,
- and design decisions needed to support downstream engineering work.

## Preferred translation approach

When translating an ATN specification into an ATN design:

1. Start from specified structure and constraints.
   - Treat the specification as authoritative.
   - Preserve its types, relations, and assertions unless an explicit assumption is needed.

2. Refine into implementable structure.
   - Introduce design elements such as components, subsystems, interfaces, connectors, stores, roles, or layers when they help realize the specification.
   - Make clear which design elements are responsible for satisfying which specified constraints.

3. Allocate responsibilities explicitly.
   - Show where behavior is realized.
   - Show which interfaces coordinate interactions.
   - Show which components own state, decisions, validation, or transformations.

4. Preserve traceability.
   - Keep the connection between specification and design visible.
   - Do not invent major functionality that is absent from the specification.

5. Make assumptions explicit.
   - If the specification leaves implementation-relevant structure open, record a small set of assumptions in prose before the ATN block.

## Avoid this pattern

Avoid designs that merely restate the specification in different words without introducing implementable structure.

Avoid designs dominated by vague placeholders such as:
- `system_component`
- `processing_module`
- `manager`
- `service`

unless their responsibilities and interfaces are clearly defined.

Do not turn every design decision into a sentence-like boolean property when a structural design element or relation would be clearer.

## Prefer this pattern

Prefer designs that make these questions answerable:
- what parts realize the specification,
- how those parts interact,
- where responsibilities are allocated,
- which interfaces carry which kinds of information or control,
- and how specified constraints are preserved by design.

## Output shape

Generated Markdown should normally contain:
- a short statement of what specification file is being refined,
- design drivers or preserved constraints,
- assumptions,
- a single ATN design in Markdown code fences,
- and short notes if useful.

The ATN block should be the center of gravity of the document.
