Let's continue to pick a numeric representation for the example in 2016-08-20.

Here are the next types we will encode. The composite type will be a product `abstract letter * letter case * final form`.

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

Here is a way of representing them.

| `abstract letter` | `Fin 5` |
| --- | --- |
| `a` | 0 |
| `b` | 1 |
| `c` | 2 |
| `d` | 3 |
| `e` | 4 |

| `letter case` | `Fin 2` |
| --- | --- |
| `uppercase` | 0 |
| `lowercase` | 1 |

| `final form` | `Fin 2` |
| --- | --- |
| `final` | 0 |
| `not final` | 1 |

Product can be represented by adding the current component value to the product of the previous cardinalities (except the first one). This makes the first component represented in the least significant digits of the representative number.

| `abstract letter` | `letter case` | `final form` | `Fin 5 * Fin 2 * Fin 2 = Fin 20` |
| --- | --- | --- | --- |
| `a` | `uppercase` | `final` | `(1 * 0) + (5 * 0) + ((5 * 2) * 0) = 0` |
| `b` | `uppercase` | `final` | `(1 * 1) + (5 * 0) + ((5 * 2) * 0) = 1` |
| `c` | `uppercase` | `final` | `(1 * 2) + (5 * 0) + ((5 * 2) * 0) = 2` |
| `d` | `uppercase` | `final` | `(1 * 3) + (5 * 0) + ((5 * 2) * 0) = 3` |
| `e` | `uppercase` | `final` | `(1 * 4) + (5 * 0) + ((5 * 2) * 0) = 4` |
| `a` | `lowercase` | `final` | `(1 * 0) + (5 * 1) + ((5 * 2) * 0) = 5` |
| `b` | `lowercase` | `final` | `(1 * 1) + (5 * 1) + ((5 * 2) * 0) = 6` |
| `c` | `lowercase` | `final` | `(1 * 2) + (5 * 1) + ((5 * 2) * 0) = 7` |
| `d` | `lowercase` | `final` | `(1 * 3) + (5 * 1) + ((5 * 2) * 0) = 8` |
| `e` | `lowercase` | `final` | `(1 * 4) + (5 * 1) + ((5 * 2) * 0) = 9` |
| `a` | `uppercase` | `not final` | `(1 * 0) + (5 * 0) + ((5 * 2) * 1) = 10` |
| `b` | `uppercase` | `not final` | `(1 * 1) + (5 * 0) + ((5 * 2) * 1) = 11` |
| `c` | `uppercase` | `not final` | `(1 * 2) + (5 * 0) + ((5 * 2) * 1) = 12` |
| `d` | `uppercase` | `not final` | `(1 * 3) + (5 * 0) + ((5 * 2) * 1) = 13` |
| `e` | `uppercase` | `not final` | `(1 * 4) + (5 * 0) + ((5 * 2) * 1) = 14` |
| `a` | `lowercase` | `not final` | `(1 * 0) + (5 * 1) + ((5 * 2) * 1) = 15` |
| `b` | `lowercase` | `not final` | `(1 * 1) + (5 * 1) + ((5 * 2) * 1) = 16` |
| `c` | `lowercase` | `not final` | `(1 * 2) + (5 * 1) + ((5 * 2) * 1) = 17` |
| `d` | `lowercase` | `not final` | `(1 * 3) + (5 * 1) + ((5 * 2) * 1) = 18` |
| `e` | `lowercase` | `not final` | `(1 * 4) + (5 * 1) + ((5 * 2) * 1) = 19` |
