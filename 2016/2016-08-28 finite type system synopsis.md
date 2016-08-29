Here is a synopsis of a finite type system.

| Type | Cardinality | Example Term Representation |
| --- | --- | --- |
| Singleton | 1 | 0 |
| Sum | sum of component cardinalities | sum of previous component cardinalities + current term representation |
| Product | product of component cardinalities | sum of each component term representation multiplied by the product of the previous components' cardinalities |
| Array | `x^len` where `x` is the component cardinality and `len` is the length of the array | a number base `x` with `len` digits |
| Function | `b^a` where `b` is the codomain cardinality and `a` is the domain cardinality | a number base `b` with `a` digits |
