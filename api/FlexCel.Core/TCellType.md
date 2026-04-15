---
uid: TCellType
description: TCellType
---

# TCellType Enumeration

This enumeration holds all the possible datatypes inside a cell\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Empty|0|The cell has no data\. Note that it might be a formatted cell, like a blank cell painted red\.<br />|
|Number|1|The cell contains a double precision floating point number\.<br />|
|DateTime|2|The cell contains a TDateTime\. **Note that Excel doesn't store datetimes inside cells** so if you are reading a TCellValue returned by FlexCel from a cell, **it will never be of type TCellValueType\.DateTime**<br /><br />DateTime is used when you want to enter a DateTime into a cell, then FlexCel will convert it to a number and enter it\. But when reading the cell value you set, it will be a number\.<br />|
|StringValue|3|The cell contains either a plain text string or a rich formatted string\.<br />|
|Boolean|4|The cell contains a boolean\.<br />|
|Error|5|The cell contains an error\.<br />|
|Formula|6|The cell contains a formula\.<br />|


