---
uid: TXlsFile.GetCellValue
description: TXlsFile.GetCellValue
---

# TXlsFile\.GetCellValue Method

## Overloads

* [TXlsFile\.GetCellValue\(Integer, Integer, Integer\)](#txlsfilegetcellvalueinteger-integer-integer)
* [TXlsFile\.GetCellValue\(Integer, Integer, Integer, Integer\)](#txlsfilegetcellvalueinteger-integer-integer-integer)

# TXlsFile\.GetCellValue\(Integer, Integer, Integer\)
Reads a Cell Value and Format\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetCellValue(const row: Integer; const col: Integer; var XF: Integer): <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|var|**XF**|Integer|XF format\.|


## Returns

Object with the value\. It can be null, a double, a string, a boolean, a [TFormula](../../FlexCel.Core/TFormula/index.md), a [TFlxFormulaErrorValue](../../FlexCel.Core/TFlxFormulaErrorValue.md) or a [TRichString](../../FlexCel.Core/TRichString/index.md)\. Dates are returned as doubles\. See the Reading Files demo to know how to use each type of the objects returned\.

## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.GetCellValue\(Integer, Integer, Integer, Integer\)
Reads a Cell Value and Format from a sheet that is not the active sheet\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetCellValue(const sheet: Integer; const row: Integer; const col: Integer; var XF: Integer): <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where is the cell you want to get the value\.|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|var|**XF**|Integer|XF format\.|


## Returns

Object with the value\. It can be null, a double, a string, a boolean, a [TFormula](../../FlexCel.Core/TFormula/index.md), a [TFlxFormulaErrorValue](../../FlexCel.Core/TFlxFormulaErrorValue.md) or a [TRichString](../../FlexCel.Core/TRichString/index.md)\. Dates are returned as doubles\. See the Reading Files demo to know how to use each type of the objects returned\.

## See also

* [TXlsFile](../TXlsFile/index.md)

