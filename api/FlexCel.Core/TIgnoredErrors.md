---
uid: TIgnoredErrors
description: TIgnoredErrors
---

# TIgnoredErrors Enumeration

Specifies what kind of errors Excel will ignore for ranges of cells\. "Errors" in a spreadsheet are the green triangles that appear in the top left corner of the cell, like "Number stored as text"\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|None|0|Don't ignore any error\.<br />|
|CalculatedColumn|1|Ignore errors when cells contain a formula different from the calculated column\.<br />|
|EmptyCellReference|2|Ignore errors of formulas pointing to empty cell references\.<br />|
|EvalError|3|Ignore errors of formulas which result in an error like \#N/A\!|
|Formula|4|Ignore erors when a fomrula isn't similar to the other formulas in the region\.<br />|
|FormulaRange|5|Ignore errors when a formula doesn't reference all cells in a range\.<br />|
|ListDataValidation|6|Ignore errors when the cell value doesn't comply with the data validation rules\.<br />|
|NumberStoredAsText|7|Ignore errors of numbers stored as text\.<br />|
|TwoDigitTextYear|8|Ignore errors when formulas contain text formatted cells with years represented as 2 digits\.<br />|
|UnlockedFormula|9|Ignore errors when unlocked cells contain formulas\.<br />|


