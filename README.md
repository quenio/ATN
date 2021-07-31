# Abstract Type Notation (ATN)

ATN is a notation to write specifications via the definition of types, constants and assertions.

It is not intended to write programs. On the contrary, it provides a declarative syntax, and supporting semantics, such as those found in type theory, lambda calculus and predicate logic.

It aims at keeping the specifications at a sufficiently abstract level, so that implementation-specific concerns do not obfuscate the clarity and the objectivity necessary in specifications.

## Types

In ATN, a type is a set that integrates its elements (a.k.a. instances) into a named concept.

## Constants

In ATN, a constant refers to a specific instance of a type. 

The same instance is always referred by the name of a constant in the whole context where such a constant is defined.

## Assertions

In ATN, assertions are expressions that should always evaluate to being true in the whole context where they have were defined.

In other words, assertions claim the truth of the proposition they define.

## Contexts

In ATN, the context is where types, constants and assertions are defined.

A sub-context can be embedded in a super-context, in which case all the definitions of the super-context are known by the sub-context, but not the other way around. A sub-context can be embedded in many super-contexts.
