---
uid: TDataConnectionFieldType
description: TDataConnectionFieldType
---

# TDataConnectionFieldType Enumeration

These are the possible data types to use when importing text into the SpreadsheetML document\. Strings are converted to these data types in the worksheet\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|General|0|The SpreadsheetML application decides the best fit data type based on the content\.<br />|
|Text|1|Field contains text\.<br />|
|MonthDayYear|2|Field contains a date in the order: month, day, year\.<br />|
|DayMonthYear|3|Field contains a date in the order: day, month, year\.<br />|
|YearMonthDay|4|Field contains a date in the order: year, month, day\.<br />|
|MonthYearDay|5|Field contains a date in the order: month, year, day\.<br />|
|DayYearMonth|6|Field contains a date in the order: day, year, month\.<br />|
|YearDayMonth|7|Field contains a date in the order: year, day, month\.<br />|
|Skip|8|Don't import this field at all\.<br />|
|EastAsianYearMonthDay|9|Field contains an East Asian date in the order: EA era year, month, day\.<br />|


