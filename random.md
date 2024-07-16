# Random functions

The functions listed on this page can be used to randomly select items or randomly generate numbers.

## Table 1. CLEM Random Functions

| Function       | Result | Description                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `oneof(LIST)`  | Any    | Returns a randomly chosen element of LIST. List items should be entered as `[ITEM1, ITEM2, ..., ITEM_N]`. Note that a list of field names can also be specified.                                                                                                                                                                                           |
| `random(NUM)`  | Number | Returns a uniformly distributed random number of the same type (INT or REAL), starting from 1 to NUM. If you use an integer, then only integers are returned. If you use a real (decimal) number, then real numbers are returned (decimal precision determined by the stream options). The largest random number returned by the function could equal NUM. |
| `random0(NUM)` | Number | This has the same properties as `random(NUM)`, but starting from 0. The largest random number returned by the function will never equal NUM.                                                                                                                                                                                                               |
