# Information functions

You can use information functions to gain insight into the values of a particular field. They're typically used to derive flag fields.

For example, the @BLANK function creates a flag field indicating records whose values are blank for the selected field. Similarly, you can check the storage type for a field using any of the storage type functions, such as `is_string`.

## Table 1. CLEM information functions

| Function         | Result  | Description                                                                                                                           |
|------------------|---------|---------------------------------------------------------------------------------------------------------------------------------------|
| @BLANK(FIELD)    | Boolean | Returns true for all records whose values are blank according to the blank-handling rules set in an upstream Type node or source node (Types tab). |
| @NULL(ITEM)      | Boolean | Returns true for all records whose values are undefined. Undefined values are system null values, displayed in SPSS Modeler as $null$.          |
| is_date(ITEM)    | Boolean | Returns true for all records whose type is a date.                                                                                    |
| is_datetime(ITEM)| Boolean | Returns true for all records whose type is a date, time, or timestamp.                                                                |
| is_integer(ITEM) | Boolean | Returns true for all records whose type is an integer.                                                                                |
| is_number(ITEM)  | Boolean | Returns true for all records whose type is a number.                                                                                  |
| is_real(ITEM)    | Boolean | Returns true for all records whose type is a real.                                                                                    |
| is_string(ITEM)  | Boolean | Returns true for all records whose type is a string.                                                                                  |
| is_time(ITEM)    | Boolean | Returns true for all records whose type is a time.                                                                                    |
| is_timestamp(ITEM)| Boolean | Returns true for all records whose type is a timestamp.                                                                               |
