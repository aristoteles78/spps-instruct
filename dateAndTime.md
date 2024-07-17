# Date and Time Functions

**Last Updated:** 2024-01-18

CLEM includes a family of functions for handling fields with datetime storage of string variables representing dates and times.

The formats of date and time used are specific to each flow and are specified in the flow properties. The date and time functions parse date and time strings according to the currently selected format.

When you specify a year in a date that uses only two digits (that is, the century is not specified), SPSS Modeler uses the default century that's specified in the flow properties.

## Table 1. CLEM Date and Time Functions

| Function | Result | Description |
| --- | --- | --- |
| @TODAY | String | If you select Rollover days/mins in the flow properties, this function returns the current date as a string in the current date format. If you use a two-digit date format and don't select Rollover days/mins, this function returns $null$ on the current server. |
| to_time(ITEM) | Time | Converts the storage of the specified field to a time. |
| to_date(ITEM) | Date | Converts the storage of the specified field to a date. |
| to_timestamp(ITEM) | Timestamp | Converts the storage of the specified field to a timestamp. |
| to_datetime(ITEM) | Datetime | Converts the storage of the specified field to a date, time, or timestamp value. |
| datetime_date(ITEM) | Date | Returns the date value for a number, string, or timestamp. Note this is the only function that allows you to convert a number (in seconds) back to a date. If ITEM is a string, creates a date by parsing a string in the current date format. The date format specified in the flow properties must be correct for this function to be successful. If ITEM is a number, it's interpreted as a number of seconds since the base date (or epoch). Fractions of a day are truncated. If ITEM is timestamp, the date part of the timestamp is returned. If ITEM is a date, it's returned unchanged. |
| date_before(DATE1, DATE2) | Boolean | Returns a value of true if DATE1 represents a date or timestamp before that represented by DATE2. Otherwise, this function returns a value of 0. |
| date_days_difference(DATE1, DATE2) | Integer | Returns the time in days from the date or timestamp represented by DATE1 to that represented by DATE2, as an integer. If DATE2 is before DATE1, this function returns a negative number. |
| date_in_days(DATE) | Integer | Returns the time in days from the baseline date to the date or timestamp represented by DATE, as an integer. If DATE is before the baseline date, this function returns a negative number. You must include a valid date for the calculation to work appropriately. For example, you should not specify 29 February 2001 as the date. Because 2001 isn't a leap year, this date doesn't exist. |
| date_in_months(DATE) | Real | Returns the time in months from the baseline date to the date or timestamp represented by DATE, as a real number. This is an approximate figure based on a month of 30.4375 days. If DATE is before the baseline date, this function returns a negative number. You must include a valid date for the calculation to work appropriately. For example, you should not specify 29 February 2001 as the date. Because 2001 isn't a leap year, this date doesn't exist. |
| date_in_weeks(DATE) | Real | Returns the time in weeks from the baseline date to the date or timestamp represented by DATE, as a real number. This is based on a week of 7.0 days. If DATE is before the baseline date, this function returns a negative number. You must include a valid date for the calculation to work appropriately. For example, you should not specify 29 February 2001 as the date. Because 2001 isn't a leap year, this date doesn't exist. |
| date_in_years(DATE) | Real | Returns the time in years from the baseline date to the date or timestamp represented by DATE, as a real number. This is an approximate figure based on a year of 365.25 days. If DATE is before the baseline date, this function returns a negative number. You must include a valid date for the calculation to work appropriately. For example, you should not specify 29 February 2001 as the date. Because 2001 isn't a leap year, this date doesn't exist. |
| date_months_difference(DATE1, DATE2) | Real | Returns the time in months from the date or timestamp represented by DATE1 to that represented by DATE2, as a real number. This is an approximate figure based on a month of 30.4375 days. If DATE2 is before DATE1, this function returns a negative number. |
| datetime_date(YEAR, MONTH, DAY) | Date | Creates a date value for the given YEAR, MONTH, and DAY. The arguments must be integers. |
| datetime_day(DATE) | Integer | Returns the day of the month from a given DATE or timestamp. The result is an integer in the range 1 to 31. |
| datetime_day_name(DAY) | String | Returns the full name of the given DAY. The argument must be an integer in the range 1 (Sunday) to 7 (Saturday). |
| datetime_hour(TIME) | Integer | Returns the hour from a TIME or timestamp. The result is an integer in the range 0 to 23. |
| datetime_in_seconds(TIME) | Real | Returns the seconds portion stored in TIME. |
| datetime_in_seconds(DATE), datetime_in_seconds(DATETIME) | Real | Returns the accumulated number, converted into seconds, from the difference between the current DATE or DATETIME and the baseline date (1900-01-01). |
| datetime_minute(TIME) | Integer | Returns the minute from a TIME or timestamp. The result is an integer in the range 0 to 59. |
| datetime_month(DATE) | Integer | Returns the month from a DATE or timestamp. The result is an integer in the range 1 to 12. |
| datetime_month_name(MONTH) | String | Returns the full name of the given MONTH. The argument must be an integer in the range 1 to 12. |
| datetime_now | Timestamp | Returns the current time as a timestamp. |
| datetime_second(TIME) | Integer | Returns the second from a TIME or timestamp. The result is an integer in the range 0 to 59. |
| datetime_day_short_name(DAY) | String | Returns the abbreviated name of the given DAY. The argument must be an integer in the range 1 (Sunday) to 7 (Saturday). |
| datetime_month_short_name(MONTH) | String | Returns the abbreviated name of the given MONTH. The argument must be an integer in the range 1 to 12. |
| datetime_time(HOUR, MINUTE, SECOND) | Time | Returns the time value for the specified HOUR, MINUTE, and SECOND. The arguments must be integers. |
| datetime_time(ITEM) | Time | Returns the time value of the given ITEM. |
| datetime_timestamp(YEAR, MONTH, DAY, HOUR, MINUTE, SECOND) | Timestamp | Returns the timestamp value for the given YEAR, MONTH, DAY, HOUR, MINUTE, and SECOND. |
| datetime_timestamp(DATE, TIME) | Timestamp | Returns the timestamp value for the given DATE and TIME. |
| datetime_timestamp(NUMBER) | Timestamp | Returns the timestamp value of the given number of seconds. |
| datetime_weekday(DATE) | Integer | Returns the day of the week from the given DATE or timestamp. |
| datetime_year(DATE) | Integer | Returns the year from a DATE or timestamp. The result is an integer such as 2021. |
| date_weeks_difference(DATE1, DATE2) | Real | Returns the time in weeks from the date or timestamp represented by DATE1 to that represented by DATE2, as a real number. This is based on a week of 7.0 days. If DATE2 is before DATE1, this function returns a negative number. |
| date_years_difference(DATE1, DATE2) | Real | Returns the time in years from the date or timestamp represented by DATE1 to that represented by DATE2, as a real number. This is an approximate figure based on a year of 365.25 days. If DATE2 is before DATE1, this function returns a negative number. |
| date_from_ywd(YEAR, WEEK, DAY) | Integer | Converts the year, week in year, and day in week, to a date using the ISO 8601 standard. |
| date_iso_day(DATE) | Integer | Returns the day in the week from the date using the ISO 8601 standard. |
| date_iso_week(DATE) | Integer | Returns the week in the year from the date using the ISO 8601 standard. |
| date_iso_year(DATE) | Integer | Returns the year from the date using the ISO 8601 standard. |
| time_before(TIME1, TIME2) | Boolean | Returns a value of true if TIME1 represents a time or timestamp before that represented by TIME2. Otherwise, this function returns a value of 0. |
| time_hours_difference(TIME1, TIME2) | Real | Returns the time difference in hours between the times or timestamps represented by TIME1 and TIME2, as a real number. If you select Rollover days/mins in the flow properties, a higher value of TIME1 is taken to refer to the previous day. If you don't
| time_in_hours(TIME) | Real | Returns the time in hours represented by TIME, as a real number. For example, under time format HHMM, the expression time_in_hours('0130') evaluates to 1.5. TIME can represent a time or a timestamp. |
| time_in_mins(TIME) | Real | Returns the time in minutes represented by TIME, as a real number. TIME can represent a time or a timestamp. |
| time_in_secs(TIME) | Integer | Returns the time in seconds represented by TIME, as an integer. TIME can represent a time or a timestamp. |
| time_mins_difference(TIME1, TIME2) | Real | Returns the time difference in minutes between the times or timestamps represented by TIME1 and TIME2, as a real number. If you select Rollover days/mins in the flow properties, a higher value of TIME1 is taken to refer to the previous day (or the previous hour, if only minutes and seconds are specified in the current format). If you don't select the rollover option, a higher value of TIME1 will cause the returned value to be negative. |
| time_secs_difference(TIME1, TIME2) | Integer | Returns the time difference in seconds between the times or timestamps represented by TIME1 and TIME2, as an integer. If you select Rollover days/mins in the flow properties, a higher value of TIME1 is taken to refer to the previous day (or the previous hour, if only minutes and seconds are specified in the current format). If you don't select the rollover option, a higher value of TIME1 causes the returned value to be negative. |