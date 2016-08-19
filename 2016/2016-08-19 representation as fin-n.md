If we have a finite type system, we should be able to represent it in a finite number. So given a collection of definitions in a finite type system, we should be able to find a natural number `n` such that all of the definitions fit in `Fin n`.

So let's look at that for each of our type system components.

#### Singleton
A singleton is a type with one inhabitant, so we can represented as a unit type like so: `n = 1` or `Fin 1`.

#### Product
A product type's cardinality is the product of the cardinalities of each of the parts. So given a product type with component cardinalities: `n1`, `n2` … `nM` (for some natural number `M`), we can represent the product type using `n = n1 * n2 * … * nM` or `Fin (n1 * n2 * … * nM)`.

#### Sum
This is the same as product but with `+` instead of `*`. Behold: A sum type's cardinality is the sum of the cardinalities of each of the parts. So given a sum type with component cardinalities: `n1`, `n2` … `nM` (for some natural number `M`), we can represent the sum type using `n = n1 + n2 + … + nM` or `Fin (n1 + n2 + … + nM)`.

#### List
To represent a list in a finite number, we will need to give a bound to its length. In other words, it's a `Vector` in the dependently-typed literature. Given a type `A` with cardinality `m`, and given a list length bound of `len` (where `m` and `len` are natural numbers), we can represent a `List A len` by `n = m ^ len` or `Fin (m ^ len)`.

Given these representations, we would need a natural number with sum, product and exponent relationships in order to express the different type cardinalities.

Given functions between types, we could optimize (in this case, minimize) the work done needed to transform a `Fin n` into a `Fin m`. The optimization work would be quite divorced from the type definitions. Although it would depend on the definitions, the definitions shouldn't depend on the numeric choices (one could hope).

For me, this finite type system represents an *interpretation* of a given `Fin n`. Mapping between types indicates a potential change of interpretation.
