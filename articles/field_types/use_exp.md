# Calculable expressions #

## Getting the value of the column ##

To get the value of the column it is necessary to use the name specified in a column properties as **Name used in formulas**.

For example, if you would like to multiply the value of the column named in formulas as **Price** by the value of the column named as **Quantity**, you can use the following expression:

**quantity*price**



## About types ##

The typization of expression calculation result is dynamic. The type is defined upon calculation. The type of the operation execution result often depends on the types of arguments, but sometimes also on the values of arguments. For example, the following expression **if(marked, sum, "Not marked")** will return either the value of the sum field or **"Not marked"** string depending on the value of the **marked** field.

The following basic types are available:

* Boolean

* String

* Number

* Date

* Time

* Table reference

* Nested table

* Picture

The values of all listed types can be compared for equality **(=)** or inequality **(!=)**.

## Types specification ##

### Boolean ###

The values of the Boolean type do not have any properties or methods.

The following operations can be performed over Boolean type values: **NOT, AND, OR**

The constants of the Boolean type are declared as **true** or **false**.



### String ###

The values of the String type do not have any properties or methods.

The strings can be concatenated with the help of **+** operator.

The following comparison operators are supported:  **<, >, <=, >=**

The constants of the String type are defined with the help of double quotes: **“String”**               



### Number ###

The values of the Number type do not have any properties or methods.

The following operations are supported: **unary -, +, -, *, /, % (remainder of the division)**

The following comparison operators are supported: **<, >, <=, >=**

The constants of the Number type are defined by the digits. A point **(.)** is used as a decimal separator.



### Date ###

The date value acquired from the **Date** type field holds only date as such, but during the calculation, if you add a **Time** type value to a **Date** type value it is possible to get a combined **Date/Time** value.    

<u>Properties:</u>

* **day** – returns the day of the month of a given date (21.01.2015 12:01 -> 21)

* **month** – returns the month of given date (21.01.2015 12:01 -> 1)

* **year** – returns the year of a given date (21.01.2015 12:01 -> 2015)

* **date** – returns the date, that does not have a time shift (21.01.2015 12:01 -> 21.01.2015)

* **time** – returns the time shift from 0:00 date (21.01.2015 12:01 -> 12:01)

The values of the **Date** type do not have any methods.

<u>The possible operations:</u>

* **addition to time** – results in a date, shifted forward for a given time

* **subtraction of time from date** – results in a date, shifted backward for a given time

* **subtraction of date from date** – results in a time, elapsed from the subtracted date

The following comparison operators are supported: **<, >, <=, >=**

### Time ###

In general is represented by a time interval. When getting the time value from the **Time** type field the value can fall within 00:00:00 to 23:59:59, but during the expression calculation the result may be more than one day.        

<u>Properties:</u>

* **days** – returns a number of days in a given time interval (1d 12:02:15 -> 1)

* **hours** – returns a number of hours in a given time interval (1d 12:02:15 -> 12)

* **minutes** – returns a number of minutes in a given time interval (1d 12:02:15 -> 2)

* **seconds** – returns a number of seconds in a given time interval (1d 12:02:15 -> 15)

* **totalhours** – returns  a total number of hours of a given time interval (1d 12:01:15 -> 36)

* **totalminutes** – returns  a total number of minutes of a given time interval (1d 12:01:15 -> 2161)

* **totalseconds** – returns  a total number of seconds of a given time interval (1d 12:01:15 -> 129675)

The values of the **Time** type do not have any methods.

<u>The possible operations:</u>  **unary -, addition to another time interval, subtraction from time interval**



### Table reference ###

Provides access to table fields through its properties. For example: **reference.column1**.

No methods are supported.



### Nested table ###

No properties are available.

<u>The following methods are supported:</u>

* **getTotal(<function>, <column name>)** – aggregates the value of a given column (passed as a the second argument) with the help of a function specified in the first argument.

For example:  **table.GetTotal(“Sum”, “column1”)**

<u>The following functions are supported:</u>

* **Sum** – a sum

* **Min** – a minimum value

* **Max** – a maximum value

* **Average** – an average value

* **Any** – at least one of the logical values is true

* **All** – all logical values are true

* **Count** – a number of non-zero values as well as the values without logical negation

* **Variance**

* **StandardDeviation**

### Picture ###

No methods or properties are available.

When comparing pictures, it is assumed that they are not equal by default.



### Methods common for all types ###

**ToString()** – converts a value into a string.


For example:

Column1 = 1

Column2 = 2

Column1 + Column2 will return the integer ‘3’,

Column1.ToString() + Column2.ToString() will return the string "12"


### The functions of conditional choice ###

**if (condition, value1, value2)** – the 1st parameter should be of logical type; the 2nd and the 3rd parameters could be of any type. If the 1st parameter is true, the function returns the 2nd parameter value, otherwise it returns the 3rd parameter value. For example: if(length(column1) > 0, "Yes", "No")

**switch (condition[0], value[0], … , value by default)** – if the condition[i] is set to true, the function returns the value[i], if the condition[i] in any i is false, the value returns by default.

### Formatting Functions ###

**format (object, mask)**, the object is of any type except child table and table reference, the mask is of string type. It returns the object’s string presentation according to the mask.

**BuildString(format, <arguments list>)** - replaces the format items in a specified string with the string representation of objects.

<u>Parameters:</u>

**format** - is a composite format string. Basically, it is represented as a static text with placeholders in specific positions. The placeholder indicates that a string representation of the parameter with a specified index (which starts from ‘0’) should be added to its position.

<u>The placeholder format:</u>
**{<parameter index>}**

For example: **BuildString("{0} of {1}", 1, 10)** will return the string "1 of 10".
Besides, it is possible to use an extended placeholder format:
**{<parameter index>[,<alignment>][:<format>]}**

**Alignment** - is an optional parameter that designates the number of characters allotted for object presentation. If the length of the string presentation is lesser than a specified value, then the remaining space will be filled with blanks to the left (in case **alignment >0**) or to the right (in case **alignment <0**).
If the length of the string presentation is greater than the alignment value, then the alignment value will be ignored.

**Format** - the format string placed after ":" has the same functionality as **format** function.

**Arguments list** – arguments of various types, converted to String value and inserted at specified position in a format string.


### Mathematical Functions ###

**sin(argument)** – calculates the argument sine. The argument is of the numeric type, the calculation result is of the numeric type.

**cos(argument)** – calculates the argument cosine. The argument is of the numeric type, the calculation result is of the numeric type.

**tan(argument)** – calculates the argument tangent. The argument is of the numeric type, the calculation result is of the numeric type.

**atan(argument)** – calculates the argument arctangent. The argument is of the numeric type, the calculation result is of the numeric type.

**sqr(argument)** – calculates the argument to square. The argument is of the numeric type, the calculation result is of the numeric type.

**sqrt(argument)** – calculates the argument‟s square root. The argument is of the numeric type, the calculation result is of the numeric type.

**log(argument)** – calculates the argument‟s natural logarithm. The argument is of the numeric type, the calculation result is of the numeric type.

**exp(argument)** – raise E number to the argument degree. The argument is of the numeric type, the calculation result is of the numeric type.

**sign(argument)** – returns:-1 if the argument is negative, 0 – if the argument is 0, 1 – if the argument is positive. The argument is of the numeric type, the calculation result is of the numeric type.

**abs(argument)** – returns the argument‟s absolute value. The argument is of the numeric type, the calculation result is of the numeric type.

**round(argument1, argument2)** – rounds the 1st argument value to the symbols amount after the comma, assigned by the 2nd argument. The 1st argument is of the double type, the 2nd argument is of the numeric type, the calculation result is of the numeric type.

### Date & Time Processing Functions ###

**getMonth (argument)** – returns the month number by the date passed by an argument.

**getMonthName (argument)** – returns the string month name by the date passed by an argument.

**getNow()** - returns the current date.

**getDayOfWeek (argument)** – returns the day of week number by the date passed by an argument.

**getDayOfWeekName (argument)** – returns the string day of week name by the date passed by an argument.

**getQuarter (argument)** – returns the quarter number of a date specified as an argument.

**addDays (argument, value)** - adds days to date. The first argument is a value of date type and the second argument is a number of days specified as numeric value. The result is a new date.

**addHours (argument, value)** - adds hours to date or time. The first argument is a value of date or time type and the second argument is a number of hours specified as a numeric value. The result is a new date or time.

**addMinutes (argument, value)** - adds minutes to date or time. The first argument is a value of date or time type and the second argument is a number of minutes specified as a numeric value. The result is a new date or time.

**addMonths (argument, value)** - adds months to date. The first argument is a value of date type and the second argument is a number of months specified as a numeric value. The result is a new date.

**addSeconds (argument, value)** - adds seconds to date or time. The first argument is a value of date or time type and the second argument is a number of seconds specified as a numeric value. The result is a new date or time.

**addYears (argument, value)** - adds years to date. The first argument is a value of date type and the second argument is a number of years specified as a numeric value. The result is a new date.

**GetWeekOfYear(weekRule, firstDayOfWeek)** – returns the week of the year for the specified **weekRule** and **firstDayOfWeek**

<u>Parameter:</u> **weekRule** – a string that defines a rule which is used to designate the first week of the year

<u>Values:</u>

**D** (First day) - indicates that the first week of the year starts on the first day of the year and ends before the following designated first day of the week. The value is 0.

**FWD** (First four day week) - indicates that the first week of the year is the first week with four or more days before the designated first day of the week. The value is 2.

**FW** (First full week) -  indicates that the first week of the year begins on the first occurrence of the designated first day of the week on or after the first day of the year. The value is 1.


<u>Parameter:</u> **firstDayOfWeek** – the first day of the week

<u>Values:</u>

**MO** - Monday, **TU** - Tuesday, **WE** - Wednesday, **TH** - Thursday, **FR** - Friday, **SA** - Saturday, **SU** - Sunday

**GetWeekOfYear()** – returns the week of the year by using **weekRule** and **firstDayOfWeek** default values. The value of both parameters may vary on different devices, that’s why it is recommended to explicitly specify the calculation method when calling the function with parameters.

For example: **column1.GetWeekOfYear("D","MO")**



### String Functions ###

**concat (string1, string2)** - returns the result of appending one string (string2) to the end of another string (string1)

**indexOf(string1, string2,[start])** - returns the position of the first occurrence of a specified value in a string; returns -1 if the value to search for never occurs. [start] – Optional parameter. Default 0. At which position to start the search.

**insert(string,position,subString)** - inserts the target string (subString) into the source string (string) at specified (position)

**length(string)** -  returns the number of characters in the string

**padLeft(string,length,char)** -  adds characters(char) to the left of a string till a certain length is reached

**padRight(string,length,char)** -  adds characters(char) to the right of a string till a certain length is reached

**remove(string,start,length)** - eliminates a range of characters in a string to a specified length (length) beginning from the (start) position

**replace (string, subString, newSubString)** - returns a string corresponding to the replacement of a given string with another in the specified string.  Input string (string), a string to be replaced (subString), a string to replace all occurrences of substring (newSubString)

**subString(string,start,length)** -  returns a substring of the specified string. If the (length) is greater than zero, the function returns a subString starting at character position (start) with a length of (length) characters. If the (length) is equal to zero, the function returns an empty string. Input string (string), position of the start of the substring (start), the length of the substring (length)

**toLower(string)** - returns the specified string converted to lowercase

**toUpper(string)** - returns the specified string converted to uppercase

**trim(string)** - returns the given string trimmed of whitespace

**trimEnd(string)** – returns the given string trimmed of trailing whitespace

**trimStart(string)** - returns the given string trimmed of leading whitespace

**regIsMatch(string,expressionString)** - returns the sign of string matching the regular expression (expressionString)

**regReplace(string, expressionString, newString)** – replaces a substring matching the regular expression (expressionString) in a (string) with a (newString)
