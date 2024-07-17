# Sequence functions

**Last Updated:** 2024-01-18

For some operations, the sequence of events is important.

The application allows you to work with the following record sequences:

- Sequences and time series
- Sequence functions
- Record indexing
- Averaging, summing, and comparing values
- Monitoring change—differentiation
- `@SINCE`
- Offset values
- Additional sequence facilities

For many applications, each record passing through a stream can be considered as an individual case, independent of all others. In such situations, the order of records is usually unimportant.

For some classes of problems, however, the record sequence is very important. These are typically time series situations, in which the sequence of records represents an ordered sequence of events or occurrences. Each record represents a snapshot at a particular instant in time; much of the richest information, however, might be contained not in instantaneous values but in the way in which such values are changing and behaving over time.

Of course, the relevant parameter may be something other than time. For example, the records could represent analyses performed at distances along a line, but the same principles would apply.

Sequence and special functions are immediately recognizable by the following characteristics:

- They are all prefixed by `@`
- Their names are given in uppercase

Sequence functions can refer to the record currently being processed by a node, the records that have already passed through a node, and even, in one case, records that have yet to pass through a node. Sequence functions can be mixed freely with other components of CLEM expressions, although some have restrictions on what can be used as their arguments.

**Examples:**

You may find it useful to know how long it has been since a certain event occurred or a condition was true. Use the function `@SINCE` to do this—for example:
`@SINCE(Income > Outgoings)`

This function returns the offset of the last record where this condition was true—that is, the number of records before this one in which the condition was true. If the condition has never been true, `@SINCE` returns `@INDEX + 1`.

Sometimes you may want to refer to a value of the current record in the expression used by `@SINCE`. You can do this using the function `@THIS`, which specifies that a field name always applies to the current record. To find the offset of the last record that had a Concentration field value more than twice that of the current record, you could use:

`@SINCE(Concentration > 2 * @THIS(Concentration))`


In some cases, the condition given to `@SINCE` is true of the current record by definition—for example:

`@SINCE(ID == @THIS(ID))`


For this reason, `@SINCE` doesn't evaluate its condition for the current record. Use a similar function, `@SINCE0`, if you want to evaluate the condition for the current record as well as previous ones; if the condition is true in the current record, `@SINCE0` returns 0.


| Function                | Result      | Description                                                                                                                                                                                                                                       |
|-------------------------|-------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| MEAN(FIELD)             | Real        | Returns the mean average of values for the specified FIELD or FIELDS.                                                                                                                                                                             |
| @MEAN(FIELD, EXPR)      | Real        | Returns the mean average of values for FIELD over the last EXPR records received by the current node, including the current record.                                                                                                               |
| @MEAN(FIELD, EXPR, INT) | Real        | Returns the mean average of values for FIELD over the last EXPR records received by the current node, including the current record. INT specifies the maximum number of values to look back.                                                    |
| @DIFF1(FIELD)           | Real        | Returns the first differential of FIELD. Returns $null$ if the relevant previous records do not exist.                                                                                                                                            |
| @DIFF1(FIELD1, FIELD2)  | Real        | Returns the first differential of FIELD1 with respect to FIELD2. Returns $null$ if the relevant previous records do not exist.                                                                                                                  |
| @DIFF2(FIELD)           | Real        | Returns the second differential of FIELD. Returns $null$ if the relevant previous records do not exist.                                                                                                                                           |
| @DIFF2(FIELD1, FIELD2)  | Real        | Returns the second differential of FIELD1 with respect to FIELD2. Returns $null$ if the relevant previous records do not exist.                                                                                                                 |
| @INDEX                  | Integer     | Returns the index of the current record. Indices are allocated as records arrive at the node, starting from 1.                                                                                                                                    |
| @LAST_NON_BLANK(FIELD)  | Any         | Returns the last non-blank value for FIELD from upstream sources. Returns $null$ if no non-blank values are found.                                                                                                                                |
| @MAX(FIELD)             | Number      | Returns the maximum value for FIELD over all records received so far.                                                                                                                                                                             |
| @MAX(FIELD, EXPR)       | Number      | Returns the maximum value for FIELD over the last EXPR records received so far, including the current record.                                                                                                                                    |
| @MAX(FIELD, EXPR, INT)  | Number      | Returns the maximum value for FIELD over the last EXPR records received so far, including the current record. INT specifies the maximum number of values to look back.                                                                           |
| @MIN(FIELD)             | Number      | Returns the minimum value for FIELD over all records received so far.                                                                                                                                                                             |
| @MIN(FIELD, EXPR)       | Number      | Returns the minimum value for FIELD over the last EXPR records received so far, including the current record.                                                                                                                                    |
| @MIN(FIELD, EXPR, INT)  | Number      | Returns the minimum value for FIELD over the last EXPR records received so far, including the current record. INT specifies the maximum number of values to look back.                                                                           |
| @OFFSET(FIELD, EXPR)    | Any         | Returns the value of FIELD from a record offset by EXPR.                                                                                                                                                                                          |
| @OFFSET(FIELD, EXPR, INT)| Any       | Returns the value of FIELD from a record offset by EXPR, with INT specifying the maximum number of values to look back.                                                                                                                           |
| @SDEV(FIELD)            | Real        | Returns the standard deviation of values for the specified FIELD or FIELDS.                                                                                                                                                                       |
| @SDEV(FIELD, EXPR)      | Real        | Returns the standard deviation of values for FIELD over the last EXPR records received by the current node, including the current record.                                                                                                         |
| @SDEV(FIELD, EXPR, INT) | Real        | Returns the standard deviation of values for FIELD over the last EXPR records received by the current node, including the current record. INT specifies the maximum number of values to look back.                                                |
| @SINCE(EXPR)            | Any         | Returns the number of records since EXPR was true.                                                                                                                                                                                                |
| @SINCE(EXPR, INT)       | Any         | Returns the number of records since EXPR was true, with INT specifying the maximum number of records to look back.                                                                                                                               |
| @SINCE0(EXPR)           | Any         | Returns 0 if EXPR is true for the current record; otherwise, returns the number of records since EXPR was true.                                                                                                                                  |
| @SINCE0(EXPR, INT)      | Any         | Returns 0 if EXPR is true for the current record; otherwise, returns the number of records since EXPR was true, with INT specifying the maximum number of records to look back.                                                                |
| @SUM(FIELD)             | Number      | Returns the sum of values for the specified FIELD or FIELDS.                                                                                                                                                                                     |
| @SUM(FIELD, EXPR)       | Number      | Returns the sum of values for FIELD over the last EXPR records received by the current node, including the current record.                                                                                                                       |
| @SUM(FIELD, EXPR, INT)  | Number      | Returns the sum of values for FIELD over the last EXPR records received by the current node, including the current record. INT specifies the maximum number of values to look back.                                                              |
| @THIS(FIELD)            | Any         | Returns the value of FIELD in the current record, used only in @SINCE expressions.                                                                                                                                                               |
