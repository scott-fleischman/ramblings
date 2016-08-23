Let's look at bidirectional maps between types. A mapping may be partial in either direction. However when defined, the mapping should be a bijection. So effectively for sets `A` and `B`, we are defining a bijection between some subset of `A` and a subset of `B`.

Finite types have a finite cardinality. So worst case (or sometimes the simplest case) is to enumerate all of the possibilities of each type, and line up the defined mappings. The component types may allow special cases based on their component structure.

#### Singletons
For a singleton `A` and singleton `B`, there is only two possibilities—either there is a mapping between the values or there isn't.

#### Sum types
For sum types, we can either articulate all of the possibilities of a component type, or use the component as a variable in the result if the result type can be constructed with a component of that type (or just ignore that component).

#### Product types
This is similar to sum types, except enumerating the combinations involves a cartesian product of the components. Likewise we can use a variable to refer to several possibilities at once to use in the result or ignore.

#### List type
The list type will need further consideration. At one extreme is listing out all possibilities. That maybe useful in simple cases but becomes tedious quickly due to the exponential explosion of possibilities. What I would especially like to see is a way to deal with different ways of articulating the expected combinations of adjacent elements.

To facilitate these mappings, it may be useful to come up with a more convenient way to create subtypes using ranges. For example, if `letter = A + B + C + D + E` then we might way to say `consonant = B – D` to indicate a range. These subtype expressions could be used in the mapping definition, similar to pattern matching in functional languages.
