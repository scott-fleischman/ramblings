Let's consider a small example in the text analysis domain.

Say we have an alphabet of five letters: A, B, C, D, E. The script includes capital and lowercase letters. The letter `c` uses the form `s` at the end of a word. In addition there is an acute accent and a diaeresis that can appear on the vowels.

Here we enumerate all of the possibilities of letters and marks. Each of these would be a singleton type.

* `A`
* `B`
* `C`
* `D`
* `E`
* `a`
* `b`
* `c`
* `s`
* `d`
* `e`
* `acute`
* `diaeresis`

We can combine them into a sum type as follows.

`symbol = A + B + C + D + E + a + b + c + s + d + e + acute + diaeresis`

We might consider a shorthand where we can define a sum type and the singletons in a single definition.

Sum types are associative. I would want the following to be equivalent, and perhaps indistinguishable in the system.

* `symbol = (A + B + C + D + E) + (a + b + c + s + d + e) + (acute + diaeresis)`
* `symbol = ((A + B + C + D + E) + (a + b + c + s + d + e)) + (acute + diaeresis)`
* `symbol = letter + mark`
  * `letter = upper-letter + lower-letter`
  * `upper-letter = A + B + C + D + E`
  * `lower-letter = a + b + c + s + d + e`
  * `mark = acute + diaeresis`

For marks, there isn't much more information to be had at this level. However, we may find it useful to have a notion of letter abstracted away from case and final forms. There are many ways to approach this—let us here define new singleton types for abstract in a namespace where we add the name `abstract`. Let us also define letter case and final forms choices. In contrast to `abstract`, the definition above for `letter` will be considered `concrete`.

* `abstract letter`
  * `a`
  * `b`
  * `c`
  * `d`
  * `e`
* `letter case`
  * `uppercase`
  * `lowercase`
* `final form`
  * `final`
  * `not final`

We may now make a mapping between `concrete letter` and `abstract letter * letter case * final form`. In our system we expect mappings to be bidirectional and map unique elements to unique elements when defined. The mappings may be partial and the system should be able to articulate all undefined pairings on either side of the mapping. Undefined pairings of either type are considered unexpected cases in the data being modeled.

Our mapping is `concrete letter <-> abstract letter * letter case * final form`. This can be represented by a table.

| `concrete letter` | `abstract letter` | `letter case` | `final form` |
| ----------------- | ----------------- | ------------- | ------------ |
| `A` | `a` | `uppercase` | `not final` |
| `B` | `b` | `uppercase` | `not final` |
| `C` | `c` | `uppercase` | `not final` |
| `D` | `d` | `uppercase` | `not final` |
| `E` | `e` | `uppercase` | `not final` |
| `a` | `a` | `lowercase` | `not final` |
| `b` | `b` | `lowercase` | `not final` |
| `c` | `c` | `lowercase` | `not final` |
| `s` | `c` | `lowercase` | `final` |
| `d` | `d` | `lowercase` | `not final` |
| `e` | `e` | `lowercase` | `not final` |

Here we have made a total mapping from `concrete letter`, so there are no undefined cases of `concrete letter`. However there are many undefined cases of `abstract letter * letter case * final form` where the item is `final`.
