Given our previous example, let's look at a basic numeric representation.

`symbol = A + B + C + D + E + a + b + c + s + d + e + acute + diaeresis`

`symbol` can be represented in `Fin 13`. One way to assign the numbers is as follows.

| `symbol` | `Fin 13` |
| `A` | 0 |
| `B` | 1 |
| `C` | 2 |
| `D` | 3 |
| `E` | 4 |
| `a` | 5 |
| `b` | 6 |
| `c` | 7 |
| `s` | 8 |
| `d` | 9 |
| `e` | 10 |
| `acute` | 11 |
| `diaeresis` | 12 |

Re-associating the `symbol`s to create subsets can still yield the same composite number.

| `upper-letter` | `Fin 5` |
| --- | --- |
| `A` | 0 |
| `B` | 1 |
| `C` | 2 |
| `D` | 3 |
| `E` | 4 |

| `lower-letter` | `Fin 6` |
| --- | --- |
| `a` | 0 |
| `b` | 1 |
| `c` | 2 |
| `s` | 3 |
| `d` | 4 |
| `e` | 5 |

One way to get a numeric representation of `Fin 5 + Fin 6` is to add `0` to the `Fin 5` number and add the `5` (from `Fin 5`) to the `Fin 6` number.

| `letter = upper-letter + lower-letter` | `Fin 5 + Fin 6 = Fin 11` |
| --- | --- |
| `A` | `0 + 0 = 0` |
| `B` | `0 + 1 = 1` |
| `C` | `0 + 2 = 2` |
| `D` | `0 + 3 = 3` |
| `E` | `0 + 4 = 4` |
| `a` | `5 + 0 = 5` |
| `b` | `5 + 1 = 6` |
| `c` | `5 + 2 = 7` |
| `s` | `5 + 3 = 8` |
| `d` | `5 + 4 = 9` |
| `e` | `5 + 5 = 10` |

| `mark = acute + diaeresis` | `Fin 2` |
| --- | --- |
| `acute` | 0 |
| `diaeresis` | 1 |

| `symbol = letter + mark` | `Fin 11 + Fin 2 = Fin 13` |
| --- | --- |
| `A` | `0 + 0 = 0` |
| `B` | `0 + 1 = 1` |
| `C` | `0 + 2 = 2` |
| `D` | `0 + 3 = 3` |
| `E` | `0 + 4 = 4` |
| `a` | `0 + 5 = 5` |
| `b` | `0 + 6 = 6` |
| `c` | `0 + 7 = 7` |
| `s` | `0 + 8 = 8` |
| `d` | `0 + 9 = 9` |
| `e` | `0 + 10 = 10` |
| `acute` | `11 + 0 = 11` |
| `diaeresis` | `11 + 1 = 12` |
