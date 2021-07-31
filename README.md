# Abstract Type Notation (ATN)

ATN is a notation to write specifications via the definition of types, constants and assertions.

It is not intended to write programs. Instead, it provides a declarative syntax, and semantics based on type theory, lambda calculus and predicate logic, to write specifications.

It aims at keeping the specifications at a sufficiently abstract level, so that implementation-specific concerns do not obfuscate the clarity and the objectivity necessary in specifications.

## Types

In ATN, a type is a [set](https://en.wikipedia.org/wiki/Set_(mathematics)) that integrates its elements (a.k.a. instances) into a named [concept](https://en.wikipedia.org/wiki/Concept).

Learn more about [types](./Types).

## Constants

In ATN, a constant refers to a specific instance of a type. 

In the whole context where such a constant is defined, its name always refers to the same instance.

## Assertions

In ATN, an assertion is a named expression that should always evaluate to being true in the whole context where it is defined.

In other words, assertions claim the truth of the proposition they define.

## Contexts

In ATN, the context is where types, constants and assertions are defined.

A context cannot have any contradictions among its definitions.

An inner-context can be embedded in an outer-context, in which case all the definitions of the outer-context are known by the inner-context, but not the other way around. There cannot be any contradictions between the inner-context and the outer-context.

An inner-context can be embedded in many outer-contexts as long as all contexts do not have contradictions among themselves.
