# Functions handling blanks and null values

Using CLEM, you can specify that certain values in a field are to be regarded as "blanks," or missing values.

The following functions work with blanks.

| Function                 | Result    | Description                                                                                                                                                                                                                                                                                            |
| ------------------------ | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `@BLANK(FIELD)`          | _Boolean_ | Returns true for all records whose values are blank according to the blank-handling rules set in an upstream Type node or Import node (Types tab).                                                                                                                                                     |
| `@LAST_NON_BLANK(FIELD)` | _Any_     | Returns the last value for _FIELD_ that was not blank, as defined in an upstream Import or Type node. If there are no nonblank values for _FIELD_ in the records read so far, `$null$` is returned. Note that blank values, also called user-missing values, can be defined separately for each field. |
| `@NULL(FIELD)`           | _Boolean_ | Returns true if the value of _FIELD_ is the system-missing `$null$`. Returns false for all other values, including user-defined blanks. If you want to check for both, use `@BLANK(FIELD)` and `@NULL(FIELD)`.                                                                                         |
| `undef`                  | _Any_     | Used generally in CLEM to enter a `$null$` value—for example, to fill blank values with nulls in the Filler node.                                                                                                                                                                                      |

Blank fields may be "filled in" with the Filler node. In both Filler and Derive nodes (multiple mode only), the special CLEM function `@FIELD` refers to the current field(s) being examined.
