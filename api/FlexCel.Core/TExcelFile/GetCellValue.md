---
uid: TExcelFile.GetCellValue
description: TExcelFile.GetCellValue
---

# TExcelFile\.GetCellValue Method

## Overloads

* [TExcelFile\.GetCellValue\(string\)](#texcelfilegetcellvaluestring)
* [TExcelFile\.GetCellValue\(Integer, Integer\)](#texcelfilegetcellvalueinteger-integer)
* [TExcelFile\.GetCellValue\(Integer, Integer, Integer\)](#texcelfilegetcellvalueinteger-integer-integer)
* [TExcelFile\.GetCellValue\(Integer, Integer, Integer, Integer\)](#texcelfilegetcellvalueinteger-integer-integer-integer)

# TExcelFile\.GetCellValue\(string\)
Reads a cell value given a cell reference\. While this is normally not needed because you can use [TCellAddress](../TCellAddress/index.md) to convert  the cell reference to row and column and then use a standard GetCellValue call, it can be handy if you know the cell reference \(like AX42\) and want a fast way to get the value of the cell\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellValue(const cellRef: string): <a href="../TCellValue/index.md">TCellValue</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cellRef**|string|Cell reference in A1 notation\. Something like A3, or Sheet1\!$B$5 can be used here\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetCellValue\(Integer, Integer\)
Reads a Cell Value\.


## Remarks

This method will return the real value stored on the cell\. For example, if you have "1\.3" formatted as "1\.30", GetCellValue will return the number 1\.3\. To get a string with the formatted value, see [GetStringFromCell\(Integer, Integer\)](GetStringFromCell.md#texcelfilegetstringfromcellinteger-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellValue(const row: Integer; const col: Integer): <a href="../TCellValue/index.md">TCellValue</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|


## Returns

Object with the value\. It can be null, a double, a string, a boolean, a [TFormula](../TFormula/index.md), a [TFlxFormulaErrorValue](../TFlxFormulaErrorValue.md) or [TRichString](../TRichString/index.md)\. Dates are returned as doubles\. See the Reading Files demo to know how to use each type of the objects returned\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetCellValue\(Integer, Integer, Integer\)
Reads a Cell Value and Format\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellValue(const row: Integer; const col: Integer; var XF: Integer): <a href="../TCellValue/index.md">TCellValue</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|var|**XF**|Integer|XF format\.|


## Returns

Object with the value\. It can be null, a double, a string, a boolean, a [TFormula](../TFormula/index.md), a [TFlxFormulaErrorValue](../TFlxFormulaErrorValue.md) or a [TRichString](../TRichString/index.md)\. Dates are returned as doubles\. See the Reading Files demo to know how to use each type of the objects returned\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetCellValue\(Integer, Integer, Integer, Integer\)
Reads a Cell Value and Format from a sheet that is not the active sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellValue(const sheet: Integer; const row: Integer; const col: Integer; var XF: Integer): <a href="../TCellValue/index.md">TCellValue</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where is the cell you want to get the value\.|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|var|**XF**|Integer|XF format\.|


## Returns

Object with the value\. It can be null, a double, a string, a boolean, a [TFormula](../TFormula/index.md), a [TFlxFormulaErrorValue](../TFlxFormulaErrorValue.md) or a [TRichString](../TRichString/index.md)\. Dates are returned as doubles\. See the Reading Files demo to know how to use each type of the objects returned\.

## See also

* [TExcelFile](../TExcelFile/index.md)

