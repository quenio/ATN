# ATN Types

Types are [sets](https://en.wikipedia.org/wiki/Set_(mathematics)) that integrate its elements (a.k.a. instances) into a named [concept](https://en.wikipedia.org/wiki/Concept).

## Specification

```haskell
TypeName :: /([A-Z]([a-z][0-9])*)+/

Type :: (name: TypeName)
```
