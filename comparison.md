Comparison functions
====================

Comparison functions are used to compare field values to each other or to a specified string.
For example, you can check strings for equality using `=`. An example of string equality verification is: `Class = "class 1"`.
For purposes of numeric comparison, *greater* means closer to positive infinity, and *lesser* means closer to negative infinity. That is, all negative numbers are less than any positive number.

Table 1. CLEM comparison functions

| Function                   | Result  | Description                                                                                                                                               |
|----------------------------|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| count_equal(ITEM1, LIST)   | Integer | Returns the number of values from a list of fields that are equal to ITEM1 or null if ITEM1 is null.                                                       |
| count_greater_than(ITEM1, LIST) | Integer | Returns the number of values from a list of fields that are greater than ITEM1 or null if ITEM1 is null.                                                   |
| count_less_than(ITEM1, LIST)    | Integer | Returns the number of values from a list of fields that are less than ITEM1 or null if ITEM1 is null.                                                      |
| count_not_equal(ITEM1, LIST)    | Integer | Returns the number of values from a list of fields that aren't equal to ITEM1 or null if ITEM1 is null.                                                    |
| count_nulls(LIST)               | Integer | Returns the number of null values from a list of fields.                                                                                                   |
| count_non_nulls(LIST)           | Integer | Returns the number of non-null values from a list of fields.                                                                                               |
| date_before(DATE1, DATE2)       | Boolean | Used to check the ordering of date values. Returns a true value if DATE1 is before DATE2.                                                                  |
| first_index(ITEM, LIST)         | Integer | Returns the index of the first field containing ITEM from a LIST of fields or 0 if the value isn't found. Supported for string, integer, and real types only.|
| first_non_null(LIST)            | Any     | Returns the first non-null value in the supplied list of fields. All storage types supported.                                                              |
| first_non_null_index(LIST)      | Integer | Returns the index of the first field in the specified LIST containing a non-null value or 0 if all values are null. All storage types are supported.        |
| ITEM1 = ITEM2                   | Boolean | Returns true for records where ITEM1 is equal to ITEM2.                                                                                                    |
| ITEM1 /= ITEM2                  | Boolean | Returns true if the two strings are not identical or 0 if they're identical.                                                                               |
| ITEM1 < ITEM2                   | Boolean | Returns true for records where ITEM1 is less than ITEM2.                                                                                                   |
| ITEM1 <= ITEM2                  | Boolean | Returns true for records where ITEM1 is less than or equal to ITEM2.                                                                                       |
| ITEM1 > ITEM2                   | Boolean | Returns true for records where ITEM1 is greater than ITEM2.                                                                                                |
| ITEM1 >= ITEM2                  | Boolean | Returns true for records where ITEM1 is greater than or equal to ITEM2.                                                                                    |
| last_index(ITEM, LIST)          | Integer | Returns the index of the last field containing ITEM from a LIST of fields or 0 if the value isn't found. Supported for string, integer, and real types only.|
| last_non_null(LIST)             | Any     | Returns the last non-null value in the supplied list of fields. All storage types supported.                                                               |
| last_non_null_index(LIST)       | Integer | Returns the index of the last field in the specified LIST containing a non-null value or 0 if all values are null. All storage types are supported.         |
| max(ITEM1, ITEM2)               | Any     | Returns the greater of the two items: ITEM1 or ITEM2.                                                                                                      |
| max_index(LIST)                 | Integer | Returns the index of the field containing the maximum value from a list of numeric fields or 0 if all values are null. For example, if the third field listed contains the maximum, the index value 3 is returned. If multiple fields contain the maximum value, the one listed first (leftmost) is returned.|
| max_n(LIST)                     | Number  | Returns the maximum value from a list of numeric fields or null if all of the field values are null.                                                       |
| member(ITEM, LIST)              | Boolean | Returns true if ITEM is a member of the specified LIST. Otherwise, a false value is returned. A list of field names can also be specified.                 |
| min(ITEM1, ITEM2)               | Any     | Returns the lesser of the two items: ITEM1 or ITEM2.                                                                                                       |
| min_index(LIST)                 | Integer | Returns the index of the field containing the minimum value from a list of numeric fields or 0 if all values are null. For example, if the third field listed contains the minimum, the index value 3 is returned. If multiple fields contain the minimum value, the one listed first (leftmost) is returned.|
| min_n(LIST)                     | Number  | Returns the minimum value from a list of numeric fields or null if all of the field values are null.                                                       |
| time_before(TIME1, TIME2)       | Boolean | Used to check the ordering of time values. Returns a true value if TIME1 is before TIME2.                                                                  |
| value_at(INT, LIST)             |         | Returns the value of each listed field at offset INT or NULL if the offset is outside the range of valid values (that is, less than 1 or greater than the number of listed fields). All storage types supported. |
