# Bitwise integer operations

These functions enable integers to be manipulated as bit patterns representing two's-complement values, where bit position N has weight 2\*\*N.

Bits are numbered from 0 upward. These operations act as though the sign bit of an integer is extended indefinitely to the left. Thus, everywhere above its most significant bit, a positive integer has 0 bits and a negative integer has 1 bit.

## Table 1. CLEM Bitwise Integer Operations

| Function                | Result  | Description                                                                                                                                                                                                                                                                                                                                                                                                  |
| ----------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `~~ INT1`               | Integer | Produces the bitwise complement of the integer INT1. That is, there is a 1 in the result for each bit position for which INT1 has 0. It is always true that `~~ INT = –(INT + 1)`.                                                                                                                                                                                                                           |
| `INT1                   |         | INT2`                                                                                                                                                                                                                                                                                                                                                                                                        | Integer | The result of this operation is the bitwise "inclusive or" of INT1 and INT2. That is, there is a 1 in the result for each bit position for which there is a 1 in either INT1 or INT2 or both.         |
| `INT1                   |         | /& INT2`                                                                                                                                                                                                                                                                                                                                                                                                     | Integer | The result of this operation is the bitwise "exclusive or" of INT1 and INT2. That is, there is a 1 in the result for each bit position for which there is a 1 in either INT1 or INT2 but not in both. |
| `INT1 && INT2`          | Integer | Produces the bitwise "and" of the integers INT1 and INT2. That is, there is a 1 in the result for each bit position for which there is a 1 in both INT1 and INT2.                                                                                                                                                                                                                                            |
| `INT1 &&~~ INT2`        | Integer | Produces the bitwise "and" of INT1 and the bitwise complement of INT2. That is, there is a 1 in the result for each bit position for which there is a 1 in INT1 and a 0 in INT2. This is the same as `INT1 && (~~INT2)` and is useful for clearing bits of INT1 set in INT2.                                                                                                                                 |
| `INT << N`              | Integer | Produces the bit pattern of INT1 shifted left by N positions. A negative value for N produces a right shift.                                                                                                                                                                                                                                                                                                 |
| `INT >> N`              | Integer | Produces the bit pattern of INT1 shifted right by N positions. A negative value for N produces a left shift.                                                                                                                                                                                                                                                                                                 |
| `INT1 &&=_0 INT2`       | Boolean | Equivalent to the Boolean expression `INT1 && INT2 /== 0` but is more efficient.                                                                                                                                                                                                                                                                                                                             |
| `INT1 &&/=_0 INT2`      | Boolean | Equivalent to the Boolean expression `INT1 && INT2 == 0` but is more efficient.                                                                                                                                                                                                                                                                                                                              |
| `integer_bitcount(INT)` | Integer | Counts the number of 1 or 0 bits in the two's-complement representation of INT. If INT is non-negative, N is the number of 1 bits. If INT is negative, it is the number of 0 bits. Owing to the sign extension, there are an infinite number of 0 bits in a non-negative integer or 1 bits in a negative integer. It is always the case that `integer_bitcount(INT) = integer_bitcount(-(INT+1))`.           |
| `integer_leastbit(INT)` | Integer | Returns the bit position N of the least-significant bit set in the integer INT. N is the highest power of 2 by which INT divides exactly.                                                                                                                                                                                                                                                                    |
| `integer_length(INT)`   | Integer | Returns the length in bits of INT as a two's-complement integer. That is, N is the smallest integer such that `INT < (1 << N)` if INT >= 0, `INT >= (–1 << N)` if INT < 0. If INT is non-negative, then the representation of INT as an unsigned integer requires a field of at least N bits. Alternatively, a minimum of N+1 bits is required to represent INT as a signed integer, regardless of its sign. |
| `testbit(INT, N)`       | Boolean | Tests the bit at position N in the integer INT and returns the state of bit N as a Boolean value, which is true for 1 and false for 0.                                                                                                                                                                                                                                                                       |