---
uid: TXlsFile.GetCellValueIndexed
description: TXlsFile.GetCellValueIndexed
---

# TXlsFile\.GetCellValueIndexed Method

Reads a Cell Value and Format, using a column index for faster access\. Normal GetCellValue\(row, col\) has to search for the column on a sorted list\. If you are looping from 1 to [TExcelFile.ColCountInRow\(Integer\)](../../FlexCel.Core/TExcelFile/ColCountInRow.md#texcelfilecolcountinrowinteger) this method is faster\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetCellValueIndexed(const sheet: Integer; const row: Integer; const colIndex: Integer; var XF: Integer): <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the cell is, 1 based\.|
|const|**row**|Integer|Row, 1 based\.|
|const|**colIndex**|Integer|Column index, 1 based\.|
|var|**XF**|Integer|XF format\.|


## Returns

Object with the value\. It can be null, a double, a string, a boolean, a [TFormula](../../FlexCel.Core/TFormula/index.md), a [TFlxFormulaErrorValue](../../FlexCel.Core/TFlxFormulaErrorValue.md) or a [TRichString](../../FlexCel.Core/TRichString/index.md)\. Dates are returned as doubles\. See the Reading Files demo to know how to use each type of the objects returned\.

## See also

* [TXlsFile](../TXlsFile/index.md)

