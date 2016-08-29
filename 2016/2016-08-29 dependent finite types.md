Let's add sigma and pi types to our finite type system and see what the representations look like.

We use some sort of dependent types in data formats all the time, such as storing a number followed by an array of that length. This is effectively a sigma type. What we see is that we don't have a number of a bounded size, but that we now have a family of bounded numbers indicated by the initial number. In effect, this gives us a range of bounded numbers for the cardinality of the sigma type.

`Sigma (len : Fin n) (array len)`

An array of length zero has cardinality `Fin 1` and type of `Fin 1` contains no information so it disappears product types. A sigma type can be thought of as a dependent pair. The cardinality of the sigma type then is as follows: `| Sigma A (B A) | = | A | * | (B A) |`. This is what you'd expect for a length followed by an array of that length. The term representation then would be the `a + |A| * (b a)`. With an `A` of 8 bytes, the term number would effectively be the 8 bytes for the length followed by an array of that length (up to a length of 255).

`Pi (a : A) (B a)`, can be thought of as a dependent function type. It's like a function type but instead of a constant cardinality like `|B| ^ |A|` for `A -> B`, each `|(B a)|` is different and is computed at the type level. The cardinality will be `|(B a1)| * |(B a2)| * … * |(B an)|`. Since the terms depend on the cardinality of the previous types, the term formula (following the examples so far) would be:

```
1 * a1 +
|(B a1)| * a2 +
|(B a1)| * |(B a2)| * a3 +
|(B a1)| * |(B a2)| * |(B a3)| * a4 +
…
|(B a1)| * ... * |(B a_{n-1})| * an
```

These formulas are sufficient to encode *specific* sigma and pi types but not general ones. That is, the type-level functions are not encoded in the system, but are external to the system.

To make the system fully dependent, we would need to encode the notion of a type of cardinality of at most `n` and allow the use of `FinSet n` in type signatures. `FinSet n` would be a set of cardinality `s : Fin n`.

I'm not sure that encoding finite sets in this manner is necessary for the purpose of interpreting the numbers. But it would allow the use of the same system for the type description and the terms.
