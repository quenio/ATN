# Abstract Type Notation (ATN)

ATN is a [notation](https://en.wikipedia.org/wiki/Notation) to write [specifications](https://en.wikipedia.org/wiki/Specification_(technical_standard)) via the definition of [types](#Types), [constants](#Constants) and [assertions](#Assertions).

It is _not_ intended to write [programs](https://en.wikipedia.org/wiki/Computer_program) or [algorithms](https://en.wikipedia.org/wiki/Algorithm). Instead, ATN provides a declarative syntax and supporting semantics (based on [type theory](https://en.wikipedia.org/wiki/Type_theory), [lambda calculus](https://en.wikipedia.org/wiki/Lambda_calculus) and [predicate logic](https://en.wikipedia.org/wiki/Higher-order_logic)) that are well-suited to write specifications.

It aims at keeping specifications at a sufficiently abstract level, so that implementation-specific concerns do not obfuscate the clarity and the objectivity necessary in specifications.

## Types

In ATN, a type is a [set](https://en.wikipedia.org/wiki/Set_(mathematics)) that integrates its elements (a.k.a. instances) into a named [concept](https://en.wikipedia.org/wiki/Concept).

Learn more about [types](./Types).

## Constants

In ATN, a constant refers to a specific instance of a type. 

In the whole context where such a constant is defined, its name always refers to the same instance.

## Assertions

In ATN, an assertion is a named expression that should always evaluate to being true within the context where it is defined.

In other words, assertions claim the truth of the proposition they define.

## Contexts

In ATN, a context is where types, constants and assertions are defined.

No context should have contradictions among its definitions.

An inner-context can be embedded in an outer-context, in which case all the definitions of the outer-context are known by the inner-context, but not the other way around. There should not be any contradictions between the inner-context and the outer-context.

An inner-context can be embedded in many outer-contexts as long as all contexts do not have contradictions among themselves.
