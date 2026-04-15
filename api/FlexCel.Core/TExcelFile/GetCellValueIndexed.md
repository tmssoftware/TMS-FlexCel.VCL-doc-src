---
uid: TExcelFile.GetCellValueIndexed
description: TExcelFile.GetCellValueIndexed
---

# TExcelFile\.GetCellValueIndexed Method

## Overloads

* [TExcelFile\.GetCellValueIndexed\(Integer, Integer, Integer\)](#texcelfilegetcellvalueindexedinteger-integer-integer)
* [TExcelFile\.GetCellValueIndexed\(Integer, Integer, Integer, Integer\)](#texcelfilegetcellvalueindexedinteger-integer-integer-integer)

# TExcelFile\.GetCellValueIndexed\(Integer, Integer, Integer\)
Reads a Cell Value and Format, using a column index for faster access\. Normal GetCellValue\(row, col\) has to search for the column on a sorted list\. If you are looping from 1 to [ColCountInRow\(Integer\)](ColCountInRow.md#texcelfilecolcountinrowinteger) this method is faster\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellValueIndexed(const row: Integer; const colIndex: Integer; var XF: Integer): <a href="../TCellValue/index.md">TCellValue</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**colIndex**|Integer|Column index, 1 based\.|
|var|**XF**|Integer|XF format\.|


## Returns

Object with the value\. It can be null, a double, a string, a boolean, a [TFormula](../TFormula/index.md), a [TFlxFormulaErrorValue](../TFlxFormulaErrorValue.md) or a [TRichString](../TRichString/index.md)\. Dates are returned as doubles\. See the Reading Files demo to know how to use each type of the objects returned\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetCellValueIndexed\(Integer, Integer, Integer, Integer\)
Reads a Cell Value and Format, using a column index for faster access\. Normal GetCellValue\(row, col\) has to search for the column on a sorted list\. If you are looping from 1 to [ColCountInRow\(Integer\)](ColCountInRow.md#texcelfilecolcountinrowinteger) this method is faster\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellValueIndexed(const sheet: Integer; const row: Integer; const colIndex: Integer; var XF: Integer): <a href="../TCellValue/index.md">TCellValue</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the cell is, 1 based\.|
|const|**row**|Integer|Row, 1 based\.|
|const|**colIndex**|Integer|Column index, 1 based\.|
|var|**XF**|Integer|XF format\.|


## Returns

Object with the value\. It can be null, a double, a string, a boolean, a [TFormula](../TFormula/index.md), a [TFlxFormulaErrorValue](../TFlxFormulaErrorValue.md) or a [TRichString](../TRichString/index.md)\. Dates are returned as doubles\. See the Reading Files demo to know how to use each type of the objects returned\.

## See also

* [TExcelFile](../TExcelFile/index.md)

