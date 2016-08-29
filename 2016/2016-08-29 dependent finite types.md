Let's add sigma and pi types to our finite type system and see what the representations look like.

We use some sort of dependent types in data formats all the time, such as storing a number followed by an array of that length. This is effectively a sigma type. What we see is that we don't have a number of a bounded size, but that we now have a family of bounded numbers indicated by the initial number. In effect, this gives us a range of bounded numbers for the cardinality of the sigma type.

`Sigma (len : Fin n) (array len)`

An array of length zero has cardinality `Fin 1` and type of `Fin 1` contains no information so it disappears product types. A sigma type can be thought of as a dependent pair. The cardinality of the sigma type then is as follows: `| Sigma A (B A) | = | A | * | (B A) |`. This is what you'd expect for a length followed by an array of that length. The term representation then would be the `a + |A| * (b a)`. With an `A` of 8 bytes, the term number would effectively be the 8 bytes for the length followed by an array of that length (up to a length of 255).

`Pi (a : A) (B a)`, can be thought of as a dependent function type. The cardinality of an individual term after we've specified `a : A` is `| (B a) | ^ | A |`, which can be thought of as an array of length `|A|` of terms of type `(B a)` (since functions and arrays are equivalent in this system). The pi type has to account for each `A` though, so what we get in the end is an collection of arrays, one array of cardinality `| (B a) | ^ | A |` for each `a : A`. Ordering the inner arrays by the order of the terms in `A`, we don't need any more information other than the inner arrays. However each element in the outer collection has a different size (namely `| (B a) | ^ | A |`) so we can't properly call the outer collection an array—it ends up being more like a tuple.

We can determine the exact cardinality of a specific pi type after we have defined it. But the cardinality of an arbitrary pi type is not known precisely because it depends on the definition, specifically, what the size of each `(B a)` type is.
