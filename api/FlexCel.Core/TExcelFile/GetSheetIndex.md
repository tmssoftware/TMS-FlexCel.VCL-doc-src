---
uid: TExcelFile.GetSheetIndex
description: TExcelFile.GetSheetIndex
---

# TExcelFile\.GetSheetIndex Method

## Overloads

* [TExcelFile\.GetSheetIndex\(string\)](#texcelfilegetsheetindexstring)
* [TExcelFile\.GetSheetIndex\(string, Boolean\)](#texcelfilegetsheetindexstring-boolean)

# TExcelFile\.GetSheetIndex\(string\)
Finds a sheet name on the workbook and returns its index\.
If it doesn't find the sheet it will raise an exception\.
See [GetSheetIndex\(string, Boolean\)](GetSheetIndex.md#texcelfilegetsheetindexstring-boolean) for a method that will not throw an exception\.
To change the active sheet by the name, use [ActiveSheetByName](ActiveSheetByName.md)\. See also [GetSheetName](GetSheetName.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetSheetIndex(const sheetName: string): Integer; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheetName**|string|Sheet you want to find\.|


## Returns

The sheet index \(1\-based\) if the sheet exists, or throws an Exception otherwise\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetSheetIndex\(string, Boolean\)
Finds a sheet name on the workbook and returns its index\.
Depending on the "throwException" parameter, this method will raise an exception or return \-1 if the sheet does not exist\.
To change the active sheet by the name, use [ActiveSheetByName](ActiveSheetByName.md)\. See also [GetSheetName](GetSheetName.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetSheetIndex(const sheetName: string; const throwException: Boolean): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheetName**|string|Sheet you want to find\.|
|const|**throwException**|Boolean|When sheetName does not exist, having throwException = true will raise an Exception\. throwException = false will  return \-1 if the sheet is not found\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

