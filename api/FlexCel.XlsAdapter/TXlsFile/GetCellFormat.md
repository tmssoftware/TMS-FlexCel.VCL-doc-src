---
uid: TXlsFile.GetCellFormat
description: TXlsFile.GetCellFormat
---

# TXlsFile\.GetCellFormat Method

## Overloads

* [TXlsFile\.GetCellFormat\(Integer, Integer\)](#txlsfilegetcellformatinteger-integer)
* [TXlsFile\.GetCellFormat\(Integer, Integer, Integer\)](#txlsfilegetcellformatinteger-integer-integer)

# TXlsFile\.GetCellFormat\(Integer, Integer\)
Cell Format for a given cell This method gets the Format number \(XF\) of a cell\.
You can create new formats using the  [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\.


## Remarks

This method DOES NOT return the format for an empty cell, even if it has a column or a row format\. For the visible format of the cell, see [TExcelFile.GetCellVisibleFormat\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/GetCellVisibleFormat.md#texcelfilegetcellvisibleformatinteger-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetCellFormat(const row: Integer; const col: Integer): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**col**|Integer|Column Index \(1 based\)|


## Returns

XF for the cell\.

## Examples

To copy the format on cell A1 to B2 you should write:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SetCellFormat(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, xls.GetCellFormat(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md)
* [TExcelFile.SetCellFormat\(Integer, Integer, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFormat.md#texcelfilesetcellformatinteger-integer-integer)
* [TExcelFile.GetFormat](../../FlexCel.Core/TExcelFile/GetFormat.md)
* [TExcelFile.GetCellVisibleFormat\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/GetCellVisibleFormat.md#texcelfilegetcellvisibleformatinteger-integer)

# TXlsFile\.GetCellFormat\(Integer, Integer, Integer\)
Cell Format for a given cell This method gets the Format number \(XF\) of a cell\.
You can create new formats using the  [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\.


## Remarks

This method DOES NOT return the format for an empty cell, even if it has a column or a row format\. For the visible format of the cell, see [TExcelFile.GetCellVisibleFormat\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/GetCellVisibleFormat.md#texcelfilegetcellvisibleformatinteger-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetCellFormat(const sheet: Integer; const row: Integer; const col: Integer): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet index \(1 based\)\.|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**col**|Integer|Column Index \(1 based\)|


## Returns

XF for the cell\.

## Examples

To copy the format on cell A1 to B2 you should write:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SetCellFormat(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, xls.GetCellFormat(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md)
* [TExcelFile.SetCellFormat\(Integer, Integer, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFormat.md#texcelfilesetcellformatinteger-integer-integer)
* [TExcelFile.GetFormat](../../FlexCel.Core/TExcelFile/GetFormat.md)
* [TExcelFile.GetCellVisibleFormat\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/GetCellVisibleFormat.md#texcelfilegetcellvisibleformatinteger-integer)

