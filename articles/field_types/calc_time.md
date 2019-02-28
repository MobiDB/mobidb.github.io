# Time difference calculation #

Date and time formulas are useful for managing features that are time or date dependent. Two data types are used for working with dates and time in MobiDB: these are **Date** and **Time** types. You can use operations like addition or subtraction on **Date** and **Time** values to calculate either a future date or elapsed time between two dates.

The date value acquired from the **Date** type field holds only date as such, but during the calculation, if you add a **Time** type value to a **Date** type value it is possible to get a combined **Date/Time** value.

The following properties are available when working with **Date** type:

* **day** – returns the day of the month of a given date (21.01.2015 12:01 -> 21)
* **month** – returns the month of given date (21.01.2015 12:01 -> 1)
* **year** – returns the year of a given date (21.01.2015 12:01 -> 2015)
* **date** – returns the date, that does not have a time shift (21.01.2015 12:01 -> 21.01.2015)
* **time** – returns the time shift from 0:00 date (21.01.2015 12:01 -> 12:01)

The values of **Date** type do not have any methods.

The available operations include:

* *addition to time* – results in a date, shifted forward for a given time
* *subtraction of time from date* – results in a date, shifted backward for a given time
* *subtraction of date from date* – results in a time, elapsed from the subtracted date

The following comparison operators are supported: <, >, <=, >=

**Time** type in general is represented by a time interval. When getting the time value from the **Time** type field the value can fall within 00:00:00 to 23:59:59, but during the expression calculation the result may be more than one day.

The following properties are available when working with **Time** type:

* **days** – returns a number of days in a given time interval (1d 12:02:15 -> 1)
* **hours** – returns a number of hours in a given time interval (1d 12:02:15 -> 12)
* **minutes** – returns a number of minutes in a given time interval (1d 12:02:15 -> 2)
* **seconds** – returns a number of seconds in a given time interval (1d 12:02:15 -> 15)
* **totalhours** – returns  a total number of hours of a given time interval (1d 12:01:15 -> 36)
* **totalminutes** – returns  a total number of minutes of a given time interval (1d 12:01:15 -> 2161)
* **totalseconds** – returns  a total number of seconds of a given time interval (1d 12:01:15 -> 129675)

The values of the **Time** type do not have any methods.

The available operations for **Time** type include:

unary -, addition to another time interval, subtraction from time interval.

Let’s have a look at the sample for better perception.

<u>***Task. To calculate worktime hours by subtracting date and time values.***</u>

In this scenario we originally have the following fields in our database:

* **Start date** (‘date1’ field) of Date type
* **Start time** (‘time1’ field) of Time type
* **End date** (‘date2’ field) of Date type
* **End time** (‘time2’ field) of Time type

To calculate working hours (subtract **Start date and time** from **End date and time**) the following approach can be used:

1. Use ***days*** property to get the number of days and multiply the result by 24 to get the number of hours
2. Subtract **Start time** from **End time** and use ***hours*** property to get the number of hours
3. Add the results  from step 1 and 2 to get the total working hours value


Example:
**(date2-date1).days*24+(time2-time1).hours**
