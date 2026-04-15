---
uid: TFormulaValueType
description: TFormulaValueType
---

# TFormulaValueType Enumeration

This enumeration contains the possible values a formula might contain\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Empty|0|The formula result is empty\.<br />|
|Number|1|The formula contains a number\.<br />|
|DateTime|2|The formula contains a TDateTime\.<br />|
|StringValue|3|The formula contains a string\.<br />|
|Boolean|4|The formula contains a boolean value\.<br />|
|Error|5|The formula result is an error\.<br />|
|MissingArg|6|This is used when a parameter for a function is missing like in the formula "=MyFunction\(1, ,3\)\. Normally it means the same as an empty value\.<br />|
|CellAddress|7|The formula contains a single cell reference\.<br />|
|CellRange|8|The formula contains a range of cells\.<br />|
|Range3D|9|The formula contains [TXls3DRange](TXls3DRange/index.md)\.<br />|
|Average|10|This is used internally when the formula is calculating an Average\.<br />The contents of the formula are of type TAverageValue\.<br /><br />This is for internal use, final formula results won't be of this type when you are doing your own user defined functions\.<br />|
|Lambda|11|The formula contains a lambda function\.<br />This is for internal use, final formula results won't be of this type when you are doing your own user defined functions\.<br />|


