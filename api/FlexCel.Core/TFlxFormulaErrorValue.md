---
uid: TFlxFormulaErrorValue
description: TFlxFormulaErrorValue
---

# TFlxFormulaErrorValue Enumeration

Error codes for cells on excel

## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|ErrNull|0|Null Value|
|ErrDiv0|7|Division by 0|
|ErrValue|15|Invalid Value|
|ErrRef|23|Invalid or deleted cell reference|
|ErrName|29|Invalid name|
|ErrNum|36|Invalid number|
|ErrNA|42|Not available|
|ErrGettingData|43|Intended to indicate when a cell reference cannot be evaluated because the value for the cell has not been retrieved or calculated\.|
|ErrCalc|48|Missing parameters for a lambda function\.<br />|
|ErrSpill|49|An array formula can't spill to adjacent cells because those cells have data\.<br />|
|ErrField|50|A field in a structured datatype doesn't exist\.<br />|
|ErrConnect|51|Error connecting to the database\.<br />|
|ErrBlocked|52|This feature is not available|
|ErrUnknown|53|Unknown error\.<br />|
|ErrPython|54|Error in the Python code\.<br />|
|ErrTimeout|55|Timeout calculating the formula\.<br />|


