---
uid: TExcelFile.GetCellFormat
description: TExcelFile.GetCellFormat
---

# TExcelFile\.GetCellFormat Method

## Overloads

* [TExcelFile\.GetCellFormat\(Integer, Integer\)](#texcelfilegetcellformatinteger-integer)
* [TExcelFile\.GetCellFormat\(Integer, Integer, Integer\)](#texcelfilegetcellformatinteger-integer-integer)

# TExcelFile\.GetCellFormat\(Integer, Integer\)
Cell Format for a given cell This method gets the Format number \(XF\) of a cell\.
You can create new formats using the  [AddFormat](AddFormat.md) function\.


## Remarks

This method DOES NOT return the format for an empty cell, even if it has a column or a row format\. For the visible format of the cell, see [GetCellVisibleFormat\(Integer, Integer\)](GetCellVisibleFormat.md#texcelfilegetcellvisibleformatinteger-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellFormat(const row: Integer; const col: Integer): Integer; overload; virtual; abstract;</code></pre>

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

* [TExcelFile](../TExcelFile/index.md)
* [AddFormat](AddFormat.md)
* [SetCellFormat\(Integer, Integer, Integer\)](SetCellFormat.md#texcelfilesetcellformatinteger-integer-integer)
* [GetFormat](GetFormat.md)
* [GetCellVisibleFormat\(Integer, Integer\)](GetCellVisibleFormat.md#texcelfilegetcellvisibleformatinteger-integer)

# TExcelFile\.GetCellFormat\(Integer, Integer, Integer\)
Cell Format for a given cell This method gets the Format number \(XF\) of a cell\.
You can create new formats using the  [AddFormat](AddFormat.md) function\.


## Remarks

This method DOES NOT return the format for an empty cell, even if it has a column or a row format\. For the visible format of the cell, see [GetCellVisibleFormat\(Integer, Integer\)](GetCellVisibleFormat.md#texcelfilegetcellvisibleformatinteger-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCellFormat(const sheet: Integer; const row: Integer; const col: Integer): Integer; overload; virtual; abstract;</code></pre>

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

* [TExcelFile](../TExcelFile/index.md)
* [AddFormat](AddFormat.md)
* [SetCellFormat\(Integer, Integer, Integer\)](SetCellFormat.md#texcelfilesetcellformatinteger-integer-integer)
* [GetFormat](GetFormat.md)
* [GetCellVisibleFormat\(Integer, Integer\)](GetCellVisibleFormat.md#texcelfilegetcellvisibleformatinteger-integer)

