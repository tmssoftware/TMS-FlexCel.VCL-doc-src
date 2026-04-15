---
uid: TAutofitMerged
description: TAutofitMerged
---

# TAutofitMerged Enumeration

Specifies how a merged cell will be autofitted\. For example, if you have a merged cell from row 1 to 4, You might want to increase the size of the first row, the second, the last, or every row a little\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|None|0|Merged cells with more than one row will not be autofitted when autofitting rows, and merged cells with more than one column will not be autofitted when autofitting rows\.<br />|
|OnLastCell|1|Autofit will change the size of the last row of the merged cell when autofitting rows, or the last column when autofitting columns\.<br />|
|OnLastCellMinusOne|2|Autofit will change the size of the row before the last row of the merged cell when autofitting rows, or the column before the last column when autofitting columns\.<br />|
|OnLastCellMinusTwo|3|Autofit will change the size of 2 rows before the last row of the merged cell when autofitting rows, or 2 columns before the last column when autofitting columns\.<br />|
|OnLastCellMinusThree|4|Autofit will change the size of 3 rows before the last row of the merged cell when autofitting rows, or 3 columns before the last column when autofitting columns\.<br />|
|OnLastCellMinusFour|5|Autofit will change the size of 4 rows before the last row of the merged cell when autofitting rows, or 4 columns before the last column when autofitting columns\.<br />|
|OnFirstCell|6|Autofit will change the size of the first row of the merged cell when autofitting rows, or the first column when autofitting columns\.<br />|
|OnSecondCell|7|Autofit will change the size of the second row of the merged cell when autofitting rows, or the second column when autofitting columns\.<br />|
|OnThirdCell|8|Autofit will change the size of the third row of the merged cell when autofitting rows, or the third column when autofitting columns\.<br />|
|OnFourthCell|9|Autofit will change the size of the fourth row of the merged cell when autofitting rows, or the fourth column when autofitting columns\.<br />|
|OnFifthCell|10|Autofit will change the size of the fifth row of the merged cell when autofitting rows, or the fifth column when autofitting columns\.<br />|
|Balanced|11|Autofit will change the height every row in the merged cell by the same amount\.<br />|


