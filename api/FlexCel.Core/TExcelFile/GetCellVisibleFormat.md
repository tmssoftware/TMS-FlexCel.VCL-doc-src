---
uid: TExcelFile.GetCellVisibleFormat
description: TExcelFile.GetCellVisibleFormat
---

# TExcelFile\.GetCellVisibleFormat Method

## Overloads

* [TExcelFile\.GetCellVisibleFormat\(Integer, Integer\)](#texcelfilegetcellvisibleformatinteger-integer)
* [TExcelFile\.GetCellVisibleFormat\(Integer, Integer, Integer\)](#texcelfilegetcellvisibleformatinteger-integer-integer)

# TExcelFile\.GetCellVisibleFormat\(Integer, Integer\)
Cell Format for a given cell, including the format of the row and the column\.


## Remarks

This might return format even if the cell is empty, if the column or the row have format\.
For the real format of the cell, see [GetCellFormat\(Integer, Integer\)](GetCellFormat.md#texcelfilegetcellformatinteger-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellVisibleFormat(const row: Integer; const col: Integer): Integer; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**col**|Integer|Column Index \(1 based\)|


## Returns

XF for the cell

## See also

* [TExcelFile](../TExcelFile/index.md)
* [AddFormat](AddFormat.md)
* [SetCellFormat\(Integer, Integer, Integer\)](SetCellFormat.md#texcelfilesetcellformatinteger-integer-integer)
* [GetFormat](GetFormat.md)
* [GetCellFormat\(Integer, Integer\)](GetCellFormat.md#texcelfilegetcellformatinteger-integer)
* [GetCellVisibleFormatDef\(Integer, Integer\)](GetCellVisibleFormatDef.md#texcelfilegetcellvisibleformatdefinteger-integer)

# TExcelFile\.GetCellVisibleFormat\(Integer, Integer, Integer\)
Cell Format for a given cell, including the format of the row and the column\.


## Remarks

This might return format even if the cell is empty, if the column or the row have format\.
For the real format of the cell, see [GetCellFormat\(Integer, Integer\)](GetCellFormat.md#texcelfilegetcellformatinteger-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellVisibleFormat(const sheet: Integer; const row: Integer; const col: Integer): Integer; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet index \(1 based\)|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**col**|Integer|Column Index \(1 based\)|


## Returns

XF for the cell

## See also

* [TExcelFile](../TExcelFile/index.md)
* [AddFormat](AddFormat.md)
* [SetCellFormat\(Integer, Integer, Integer\)](SetCellFormat.md#texcelfilesetcellformatinteger-integer-integer)
* [GetFormat](GetFormat.md)
* [GetCellFormat\(Integer, Integer\)](GetCellFormat.md#texcelfilegetcellformatinteger-integer)
* [GetCellVisibleFormatDef\(Integer, Integer\)](GetCellVisibleFormatDef.md#texcelfilegetcellvisibleformatdefinteger-integer)

