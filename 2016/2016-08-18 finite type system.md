What if we created a type system meant only for finite sets? I would like it as simple as possible. I'm not concerned about representing all of mathematics in the system, but only actually finite data sets. I've been coming to the conclusion that such a system would be useful for analysis on data sets such as texts of ancient languages.

Let's say we only have the following primitives.
* Singleton type
* Composite types
  * Product type
  * Sum type
  * List type

That sounds simple enough for me. The singleton type is our primitive. We can create as many as we want by giving a unique name. Maybe we add a namespace which could function like a product type of names.

Composite types require uniquely typed components. The uniqueness constraint will allow us to get traversals (including lenses and prisms) for free. For example, given some composite `C` containing a type `A`, since there is exactly one `A` in the entire composite hierarchy, we can create a composite of traversals (with lenses and prisms) without having to specify that. That way I can apply a function `A -> B` to the type `C` to get a type `D` where the type `A` is replaced by `B`.

This type system is meant for analysis, so I won't require total functions. The reason is that I generally am transforming a larger set into a smaller set with more information about what *actually* occurs in a finite data set. Partial functions effectively validate the data against the model. The system or machine that does the work of applying the partial functions will validate that the partial functions handle all of the cases in the input data sets.

I would like the definition of functions to always be bidirectional. That way when we define a partial function `A -> B` we are also defining a partial function `B -> A`. I hope that this pair of functions will be inverses of each other in some sense. It will also require that the pairing be between unique elements on both sides.

I would also like to define the function only once with the pairings. Such as:

* `A1 <-> B3`
* `A2 <-> B2`
* `A3 <-> B1`

If there are more than 3 elements in `A`, then `A -> B` is partial. Likewise if there are more than 3 elements in `B` then `B -> A` is also partial.

The system/UI in which you define this function pair should show you the undefined cases if the functions are partial.
