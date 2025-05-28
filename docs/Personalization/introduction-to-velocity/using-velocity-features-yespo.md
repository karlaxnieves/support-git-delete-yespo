---
title: Using Velocity Features in Yespo
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Using Velocity Features in Yespo | Yespo Guide
  description: >-
    Guide on using the Apache Velocity library in Yespo: extracting data,
    handling arrays, loops, conditions, arithmetic, date formatting, and string
    manipulation.
  robots: index
next:
  description: ''
---
Our system features the dynamic content option using the <a rel="nofollow" href="https://velocity.apache.org/engine/1.7/user-guide.html" target="_blank">Apache Velocity</a> library. Let’s review the most common Velocity features to use in Yespo.

## Getting the single parameter

All external data is contained in the data object. To extract it to the message, use command _$!data.get_ and specify the parameter name you want to extract:

```json
$!data.get('parameter name')
```

## Getting array elements by index

To get the array element by its index, specify the name of the array and the element’s index:

```json
$!data.get('array name').get(0)
```

— if array contains only values, where 0 is the element's index (array indexes in JSON are 0-based).

```json
$!data.get('array name').get(0).get('parameter name')
```

— if array contains objects with parameters.

This method is suitable when you know the array’s size in advance. If you specify the element's index that does not exist in the array, an error will occur when sending a message.

## Get the array size

Syntax:

```json
$!data.get('array name').size()
```

## Loop to get all the array elements

Use the `#foreach` loop.

Syntax:

```json
#foreach($item in $data.get('array name'))
$velocityCount: $item.get('name') ...
#end
```

`$item` is a variable assigned to the current array element and can be accessed inside the loop. In this case, the entire list of elements in the array will be displayed one by one; `$velocityCount` — the default name of the loop counter, its initial value starts from 1.

If you want to stop the `#foreach` loop, use the #break directive to stop the loop on the condition you want:

```json
#foreach($item in $data.get('array name'))
$velocityCount: $item.get('name') ...
#if( $velocityCount > 5 ) #break #end
#end
```

## Assignment

The `'value'` variable can refer to specific values, other variables, or expressions.

Syntax:

```json
#set($var='value')
```

## Comparison

Comparison and logical operators:

| Velocity comparison operators | Corresponding comparison operations |
| :---------------------------- | :---------------------------------- |
| gt                            | > (more)                            |
| lt                            | \< (less)                           |
| ge                            | ≥ (more or equal)                   |
| le                            | ≤ (less or equal)                   |
| ==                            | = (equal)                           |
| !=                            | ≠ (not equal)                       |
| and                           | && (logical AND)                    |
| or                            | \|\| (logical OR)                   |
| not                           | ! (logical NOT)                     |

Syntax:

```json
$!param1 gt $!param2
```

Also, you can use operators to compare strings with and without case sensitivity.

Syntax:

```json
$!firstString.equals($!secondString)
$!firstString.equalsIgnoreCase($!secondString)
```

## Condition

Use conditions in such cases:

- if you need to get only some specific data (for example, only one product category);
- if you need to display a certain amount of products in one block so as not to break the message layout.

Syntax:

```json
#if ($data.get('params')=='value')
(content)
#end
```

If the condition is not met, you can display an alternative:

```json
#if($data.get('param')=='value')
(content)
#else
(alternate content)
#end
```

You can also check several conditions:

```
#if($data.get('param')=='value1')
(content 1)
#elseif($data.get('param')=='value2')
(content 2)
#else
(alternate content)
#end
```

You can combine several conditions using the logical operators `and / or`:

```json
#if ($data.get('param1')=='value1' and $data.get('param2')=='value2')
(content)
#end
```

To invert the condition use syntax:

```json
#if (!($data.get('param')=='value'))
(content)
#end
```

## Arithmetic operations

Addition:

```json
$mathTool.add($v1, $v2)
```

Subtraction:

```json
$mathTool.sub($v1, $v2)
```

Multiplication:

```json
$mathTool.mul($v1, $v2)
```

Division:

```json
$mathTool.div($v1, $v2)
```

## Number formatting

Output of an integer without rounding:

```json
$numberTool.integer($v1)
```

Output of money amounts with two decimal places:

```json
$!numberTool.format('#.00',$v1)
```

## Date displaying in message

Output of the current date:

```json
$!dateTool.currentDate()
```

Output of the Unix TimeStamp (current date in milliseconds):

```json
$!dateTool.currentTimeStamp()
```

Output of the date and/or time, the second argument can be set to Greenwich Mean Time (GMT):

```json
$!dateTool.currentDate('dd.MM.yyyy HH:mm:ss', 'GMT+3')
```

If the date is passed in the Unix TimeStamp format (for example, 1495479520000), convert it to a readable format using the function:

```json
$!dateTool.formatDate('dd.MM.yyyy',$!data.get('date'))
```

or specifying the format:

```json
$!dateTool.formatDate('yyyy-MM-dd HH:mm:ss',$!data.get('date'))
```

To format the entry date in the contact’s time zone, use

```
$!dateTool.formatInContactTimezone(String format, String dateTime)
```

where the date format must be in ISO 8601:

- dd/MM/yyyy HH:mm:ss
- yyyy-MM-dd'T'HH:mm:ss
- yyyy-MM-dd'T'HH:mm:ss'Z'

The organization time zone is applied if the contact's time zone is not specified.

The output formats are described <a rel="nofollow" href="https://docs.oracle.com/javase/8/docs/api/java/text/SimpleDateFormat.html" target="_blank">here</a>.

## Operations with dates

Add to the date the required number of units (year, month, day, hour, minutes). If you get a date like this from an event or an additional field: "date":"01/01/2020 12:00", the result of the operation will be as follows:

```json
$!dateTool.addYears($!data.get('date'),2) -> 01/01/2022 12:00
$!dateTool.addMonths($!data.get('date'),5) -> 01/06/2020 12:00
$!dateTool.addDays($!data.get('date'),15) -> 16/01/2020 12:00
$!dateTool.addHours($!data.get('date'),7) -> 01/01/2020 19:00
$!dateTool.addMinutes($!data.get('date'),15) -> 01/01/2020 12:15
```

if the second argument is negative, the subtraction result will be returned.

By default, a date is expected in one of the listed formats.

- dd/MM/yyyy HH:mm
- dd/MM/yyyy
- yyyy-MM-dd'T'HH:mm
- yyyy-MM-dd

If the format is different, set your own format as the third argument. For example, if the date you pass in the format "customDate": "12:00 2020-30-04", the expression will take the form:

```json
$!dateTool.addYears($!data.get('customDate'),2,'HH:mm yyyy-dd-MM') -> 12:00 2022-30-04
```

Similarly, by specifying the fourth argument, you can format the date, for example, if the date is in the format: "dateTime":"2020-05-01T00:00":

```json
$!dateTool.addDays($!data.get('dateTime'), 2, "yyyy-MM-dd'T'HH:mm",'dd-MM-yyyy') -> 03-05-2020
$!dateTool.addHours($!data.get('dateTime'), 7, "yyyy-MM-dd'T'HH:mm",'dd/MM HH:mm') -> 01/05 07:00
$!dateTool.addMinutes($!data.get('dateTime'), 2, "yyyy-MM-dd'T'HH:mm",'HH:mm') -> 00:02
```

Calculating the difference of two dates in (minutes, days, months and years) "firstDate":"01/01/2019", "secondDate":"05/05/2020":

```json
$!dateTool.diff($!firstDate,$!secondDate,'YEARS') -> 1
$!dateTool.diff($!firstDate,$!secondDate,'MONTHS') -> 16
$!dateTool.diff($!firstDate,$!secondDate,'DAYS') -> 490
$!dateTool.diff($!firstDate,$!secondDate,'HOURS') -> 11760
$!dateTool.diff($!firstDate,$!secondDate,'MINUTES') -> 705600
```

To calculate the difference, both dates must be in the same format, if your format differs from the default expected, the fourth argument can be a custom format, for example, for two dates: "customDate1":"17:15 05/05/2020", "customDate2 ":"10:05 01/01/2019":

```json
$!dateTool.diff($!customDate1,$!customDate2,'HH:mm dd/MM/yyyy','MINUTES') -> 706030
```

## Checking for a non-empty value

If you need to check whether a parameter was passed and whether it was empty, use the following code:

```json
#if($data.get('param') and $data.get('param')!=’’)
(content)
#end
```

Usage: if the message contains an appeal to the user by name, but not all users have name parameters in the code.

## Working with strings

Get the string length:

```json
$!var.length()
```

Get the string part:

```json
$!var.substring(start index, end index)
```

Replace the part of the string with a different value:

```json
$!var.replace('what needs to be changed','value to set instead')
```

Change the case of a string:

```json
#set ($example = "UkRaInE")  
$example.toUpperCase()  // UKRAINE
$example.toLowerCase()  // ukraine
```