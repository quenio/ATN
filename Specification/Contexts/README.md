# ATN Contexts

A context is where types, constants and assertions are defined.

## Specification

```haskell
Context

outer_contexts: Context -> {Context}
inner_contexts: Context -> {Context}
```
