String functions
====================
With CLEM, you can run operations to compare strings, create strings, or access characters.

In CLEM, a string is any sequence of characters between matching double quotation marks ("string quotes"). Characters (CHAR) can be any single alphanumeric character. They're declared in CLEM expressions using single back quotes in the form of `<character>`, such as `z`, `A`, or `2`. Characters that are out-of-bounds or negative indices to a string will result in undefined behavior.
## Table 1. CLEM string functions
| Function                   | Result  | Description                                                                                                                                               |
|----------------------------|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| allbutfirst(N, STRING)                | String   | Returns a string, which is STRING with the first N characters removed.                                                                                                            |
| allbutlast(N, STRING)               | String    | Returns a string, which is STRING with the last characters removed.                                                                                                 |
| alphabefore(STRING1, STRING2)                | Boolean    | Used to check the alphabetical ordering of strings. Returns true if STRING1 precedes STRING2.                                                                                                              |
| count_substring(STRING, SUBSTRING)               | Integer    | Returns the number of times the specified substring occurs within the string. For example, count_substring("foooo.txt", "oo") returns 3.                                                                                                   |
| endstring(LENGTH, STRING)               | String    | Extracts the last N characters from the specified string. If the string length is less than or equal to the specified length, then it is unchanged.                                                                                                          |
| arctan2(NUM_Y, NUM_X)      | Real    | Computes the arctangent of NUM_Y / NUM_X and uses the signs of the two numbers to derive quadrant information. The result is a real in the range - pi < ANGLE <= pi (radians) – 180 < ANGLE <= 180 (degrees) |
| arctanh(NUM)               | Real    | Computes the hyperbolic arctangent of the specified angle.                                                                                                |
| cos(NUM)                   | Real    | Computes the cosine of the specified angle.                                                                                                               |
| cosh(NUM)                  | Real    | Computes the hyperbolic cosine of the specified angle.                                                                                                    |
| pi                         | Real    | This constant is the best real approximation to pi.                                                                                                       |
| sin(NUM)                   | Real    | Computes the sine of the specified angle.                                                                                                                 |
| sinh(NUM)                  | Real    | Computes the hyperbolic sine of the specified angle.                                                                                                      |
| tan(NUM)                   | Real    | Computes the tangent of the specified angle.                                                                                                              |
| tanh(NUM)                  | Real    | Computes the hyperbolic tangent of the specified angle.                                                                                                   |



