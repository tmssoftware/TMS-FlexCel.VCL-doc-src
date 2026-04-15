---
uid: TExcelFile.GetCellVisibleFormatDef
description: TExcelFile.GetCellVisibleFormatDef
---

# TExcelFile\.GetCellVisibleFormatDef Method

## Overloads

* [TExcelFile\.GetCellVisibleFormatDef\(Integer, Integer\)](#texcelfilegetcellvisibleformatdefinteger-integer)
* [TExcelFile\.GetCellVisibleFormatDef\(Integer, Integer, Integer\)](#texcelfilegetcellvisibleformatdefinteger-integer-integer)

# TExcelFile\.GetCellVisibleFormatDef\(Integer, Integer\)
Cell Format for a given cell, including the format of the row and the column\.


## Remarks

This might return format even if the cell is empty, if the column or the row have format\.
For the real format of the cell, see [GetCellFormat\(Integer, Integer\)](GetCellFormat.md#texcelfilegetcellformatinteger-integer) This is a shortcut for GetCellVisibleFormat, returning the final Format struct\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellVisibleFormatDef(const row: Integer; const col: Integer): <a href="../TFlxFormat/index.md">TFlxFormat</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**col**|Integer|Column Index \(1 based\)|


## Returns

Format for the cell

## See also

* [TExcelFile](../TExcelFile/index.md)
* [AddFormat](AddFormat.md)
* [SetCellFormat\(Integer, Integer, Integer\)](SetCellFormat.md#texcelfilesetcellformatinteger-integer-integer)
* [GetFormat](GetFormat.md)
* [GetCellFormat\(Integer, Integer\)](GetCellFormat.md#texcelfilegetcellformatinteger-integer)
* [GetCellVisibleFormat\(Integer, Integer\)](GetCellVisibleFormat.md#texcelfilegetcellvisibleformatinteger-integer)

# TExcelFile\.GetCellVisibleFormatDef\(Integer, Integer, Integer\)
Cell Format for a given cell, including the format of the row and the column\.


## Remarks

This might return format even if the cell is empty, if the column or the row have format\.
For the real format of the cell, see [GetCellFormat\(Integer, Integer\)](GetCellFormat.md#texcelfilegetcellformatinteger-integer) This is a shortcut for GetCellVisibleFormat, returning the final Format struct\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellVisibleFormatDef(const sheet: Integer; const row: Integer; const col: Integer): <a href="../TFlxFormat/index.md">TFlxFormat</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet index\. \(1 based\)|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**col**|Integer|Column Index \(1 based\)|


## Returns

Format for the cell

## See also

* [TExcelFile](../TExcelFile/index.md)
* [AddFormat](AddFormat.md)
* [SetCellFormat\(Integer, Integer, Integer\)](SetCellFormat.md#texcelfilesetcellformatinteger-integer-integer)
* [GetFormat](GetFormat.md)
* [GetCellFormat\(Integer, Integer\)](GetCellFormat.md#texcelfilegetcellformatinteger-integer)
* [GetCellVisibleFormat\(Integer, Integer\)](GetCellVisibleFormat.md#texcelfilegetcellvisibleformatinteger-integer)

