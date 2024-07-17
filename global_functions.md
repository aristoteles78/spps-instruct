# Global functions

The functions `@MEAN`, `@SUM`, `@MIN`, `@MAX`, and `@SDEV` work on, at most, all of the records read up to and including the current one. In some cases, however, it is useful to be able to work out how values in the current record compare with values seen in the entire data set. Using a Set Globals node to generate values across the entire data set, you can access these values in a CLEM expression using the global functions.

For example, @GLOBAL_MAX(Age) returns the highest value of Age in the data set, while the expression (Value - @GLOBAL_MEAN(Value)) / @GLOBAL_SDEV(Value) expresses the difference between this record's Value and the global mean as a number of standard deviations. You can use global values only after they have been calculated by a Set Globals node.

## Table 1. CLEM global functions

| Function              | Result   | Description                                                                                                                                                                                                                                                    |
| --------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `@GLOBAL_MAX(FIELD)`  | _Number_ | Returns the maximum value for _FIELD_ over the whole data set, as previously generated by a Set Globals node. _FIELD_ must be the name of a numeric, date/time/datetime, or string field. If the corresponding global value has not been set, an error occurs. |
| `@GLOBAL_MIN(FIELD)`  | _Number_ | Returns the minimum value for _FIELD_ over the whole data set, as previously generated by a Set Globals node. _FIELD_ must be the name of a numeric, date/time/datetime, or string field. If the corresponding global value has not been set, an error occurs. |
| `@GLOBAL_SDEV(FIELD)` | _Number_ | Returns the standard deviation of values for _FIELD_ over the whole data set, as previously generated by a Set Globals node. _FIELD_ must be the name of a numeric field. If the corresponding global value has not been set, an error occurs.                 |
| `@GLOBAL_MEAN(FIELD)` | _Number_ | Returns the mean average of values for _FIELD_ over the whole data set, as previously generated by a Set Globals node. _FIELD_ must be the name of a numeric field. If the corresponding global value has not been set, an error occurs.                       |
| `@GLOBAL_SUM(FIELD)`  | _Number_ | Returns the sum of values for _FIELD_ over the whole data set, as previously generated by a Set Globals node. _FIELD_ must be the name of a numeric field. If the corresponding global value has not been set, an error occurs.                                |