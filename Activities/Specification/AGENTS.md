# AGENTS

Instructions for work under `Activities/Specification`.

These instructions are especially important when using `./atn spec` to translate a Markdown requirements document into an ATN specification.

## Goal of translation

The goal is not to mechanically restate English requirements as long boolean predicate names.

The goal is to produce an ATN specification that captures the structure of the subject matter:
- the main types in the domain,
- the constants and relations between them,
- and the assertions that constrain valid states and valid behavior.

Prefer a structural ATN model over a compliance-checklist ATN model.

If forced to choose, omit secondary prose requirements rather than replacing the subject matter with a forest of sentence-like boolean predicates.

## Preferred translation approach

When translating a source document into ATN:

1. Identify the domain vocabulary.
   - What are the main entities, roles, message kinds, resources, states, capabilities, or values?
   - Introduce ATN types for these domain concepts.

2. Identify structure before rules.
   - Define the important constants, functions, and relations that describe the shape of the domain.
   - For protocols and schemas, model the actual objects and links between them.

3. State constraints as assertions.
   - Use assertions to express invariants, admissibility conditions, exclusivity conditions, dependency conditions, and consistency rules.
   - Prefer short, meaningful assertion names.

4. Make assumptions explicit.
   - If the source is ambiguous or too broad, record a small set of explicit assumptions in prose before the ATN block.
   - Do not silently collapse a plural domain into one representative object unless the source scope is explicitly singular.

## Avoid this pattern

Avoid specifications dominated by predicates like these:
- `requires_explicit_user_consent_before_tool_invocation: Protocol -> Boolean`
- `requests_have_non_null_unique_string_or_integer_ids_within_sessions: Protocol -> Boolean`

Those mostly restate prose in predicate names and do not model the domain itself.

More generally, avoid introducing a boolean-valued function when all of the following are true:
- its name is essentially a full English sentence,
- it exists only to encode one requirement line,
- it does not correspond to a domain concept that can vary independently,
- and it is not needed as a reusable part of multiple assertions.

Do not create a representative object such as `protocol`, `implementation`, `system`, or `document` merely to hang many sentence-like booleans off it.

## Prefer this pattern

Prefer modeling the domain directly. For example, for a protocol, first model things like:
- `Session`
- `Message`
- `Request`
- `Response`
- `Notification`
- `Client`
- `Server`
- `Capability`
- `Tool`
- `Resource`
- `Prompt`
- `Task`

Then define structure such as:
- request identifiers,
- message kinds,
- response-to-request relationships,
- capability declarations,
- tool schemas,
- task states,
- subscriptions,
- and similar protocol structure.

Then express rules as assertions, such as:
- notifications do not carry request IDs,
- responses correspond to requests,
- request IDs are unique within a session,
- terminal task states do not transition further,
- a resource update notification requires a prior subscription,
- and so on.

A good ATN translation should let a reader answer:
- what kinds of things exist in the domain,
- how those things are related,
- and what combinations or transitions are valid.

A poor ATN translation only lets a reader answer:
- which prose requirements were restated.

## Normative language

Translate the source strength faithfully:
- `MUST`, `REQUIRED`, and equivalent mandatory statements should usually become ATN assertions.
- `SHOULD` guidance should usually remain in prose notes unless the document is explicitly modeling recommendations as first-class concepts.
- `MAY` permissions should not be turned into mandatory assertions.

Do not accidentally strengthen optional or advisory source text into hard constraints.

## Naming guidance

- Prefer short domain names over sentence-like names.
- Use names that reveal structure, not English commentary.
- Keep assertion names readable and specific.
- Reuse source terminology where practical.
- Prefer names like `request_id`, `response_to`, `server_offers_tool`, `task_status`, and `resource_uri`.
- Avoid names like `requests_must_have_unique_ids_within_a_session` as functions; that belongs as an assertion over simpler names.

## Protocol and schema documents

When the source document is a protocol, API, or schema:
- model the protocol objects, not just the policy statements;
- model fields, associations, allowed message forms, and cross-message constraints;
- distinguish message structure from transport rules and from security guidance;
- keep the ATN specification centered on the protocol's ontology and invariants.

For a protocol or schema translation, the ATN specification should usually contain most of these before it contains policy-style assertions:
- participant or actor types,
- message or document types,
- identifiers and key value types,
- structural relations between messages or entities,
- optional feature or capability relations,
- state or status types where the source defines stateful behavior.

Security, consent, operational, and transport constraints should usually be written as assertions over this structural model, not as separate sentence-like boolean properties.

## Translation quality checks

Before finalizing a generated specification, check the following:
- Does the ATN block define the main domain types explicitly?
- Are most mandatory requirements expressed as assertions over simple structural relations?
- Would deleting all long sentence-like boolean functions leave the core model mostly intact? If not, the model is too checklist-oriented.
- For a protocol, can a reader see messages, participants, identifiers, capabilities, states, and their relations?
- Are `SHOULD` and `MAY` statements being handled without accidentally turning them into hard constraints?

If the answer to the first four questions is not clearly yes, revise the model toward structure.

## Output shape

Generated Markdown should normally contain:
- a short statement of what source file is being translated,
- extracted requirements,
- assumptions,
- a single ATN specification in Markdown code fences,
- and short notes if useful.

The ATN block should be the center of gravity of the document.
