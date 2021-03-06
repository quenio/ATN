# Abstract Type Notation (ATN)

ATN is a [notation](https://en.wikipedia.org/wiki/Notation) to write [specifications](https://en.wikipedia.org/wiki/Specification_(technical_standard)) via the definition of [types](#Types), [constants](#Constants) and [assertions](#Assertions).

It is _not_ intended to write [programs](https://en.wikipedia.org/wiki/Computer_program) or [algorithms](https://en.wikipedia.org/wiki/Algorithm). Instead, ATN provides a declarative syntax and supporting semantics (based on [set theory](https://en.wikipedia.org/wiki/Set_theory), [type theory](https://en.wikipedia.org/wiki/Type_theory), [lambda calculus](https://en.wikipedia.org/wiki/Lambda_calculus) and [predicate logic](https://en.wikipedia.org/wiki/Higher-order_logic)) that are well-suited to write specifications.

It aims at keeping specifications at a sufficient level of [abstraction](https://en.wikipedia.org/wiki/Abstraction), so that [implementation](https://en.wikipedia.org/wiki/Implementation)-specific concerns do not obfuscate the clarity and the [objectivity](https://en.wikipedia.org/wiki/Objectivity_(philosophy)) necessary in specifications.

Multiple specifications can be organized in separate [contexts](#Contexts).

> "Abstractions are not a luxury, but a necessity. Thought is man's guide to action. Reason is a practical attribute.", by
> [Leonard Peikoff](https://en.wikipedia.org/wiki/Leonard_Peikoff) in [Objectivism: The Philosophy of Ayn Rand](https://en.wikipedia.org/wiki/Objectivism:_The_Philosophy_of_Ayn_Rand)


## Definitions

### Types

In ATN, a type is a [set](https://en.wikipedia.org/wiki/Set_(mathematics)) that integrates its elements (a.k.a. instances) into a named [concept](https://en.wikipedia.org/wiki/Concept).

Learn more about [types](./Types).

### Constants

In ATN, a constant refers to a specific instance of a type. 

In the whole context where such a constant is defined, its name always refers to the same instance.

Learn more about [constants](./Constants).

### Assertions

In ATN, an assertion is a named expression that should always evaluate to being true within the context where it is defined.

In other words, assertions claim the truth of the proposition they define.

Learn more about [assertions](./Assertions).

### Contexts

In ATN, a context is where types, constants and assertions are defined.

No context should have [contradictions](https://en.wikipedia.org/wiki/Contradiction) among its definitions.

An inner-context can be embedded in an outer-context, in which case all the definitions known by the outer-context are also known by the inner-context, but not the other way around. There should not be any contradictions between the inner-context and the outer-context.

An inner-context may be embedded in many outer-contexts as long as all involved contexts do not have contradictions among themselves.

All contexts of any specifications defined in ATN are automatically embbeded in ATN's outermost context (named `world`), which defines core types, such as `Boolean`, `Character`, `String`, `Natural`, `Real`, among others. That means no specifications should contradict the definitions of ATN's world.

## Examples

ATN can be used to specify anything, from programs to processes, from physical systems to theories. Anything that can be integrated into concepts of a mind can be specified in ATN.

Below, some examples are shown that demonstrate the expressive power of ATN in specifications.
