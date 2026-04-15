---
uid: TExcelFile.GetRowHeight
description: TExcelFile.GetRowHeight
---

# TExcelFile\.GetRowHeight Method

## Overloads

* [TExcelFile\.GetRowHeight\(Integer\)](#texcelfilegetrowheightinteger)
* [TExcelFile\.GetRowHeight\(Integer, Boolean\)](#texcelfilegetrowheightinteger-boolean)
* [TExcelFile\.GetRowHeight\(Integer, Integer, Boolean\)](#texcelfilegetrowheightinteger-integer-boolean)

# TExcelFile\.GetRowHeight\(Integer\)
Returns the current Row height, in Excel internal units\. \(1/20th of a point\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TFlxConsts.RowMult](../TFlxConsts/RowMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetRowHeight(const row: Integer): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row Index \(1 based\)|


## Returns

Row height in internal excel units\.

## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RowHeightInPixels := xls.GetRowHeight(Row) / TFlxConsts.RowMult;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetRowHeight\(Integer, Boolean\)
Returns the current Row height, in Excel internal units\. \(1/20th of a point\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TFlxConsts.RowMult](../TFlxConsts/RowMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetRowHeight(const row: Integer; const HiddenIsZero: Boolean): Integer; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**HiddenIsZero**|Boolean|If true, the height returned for a hidden row will be 0 and not its real height\.|


## Returns

Row height in internal excel units\.

## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RowHeightInPixels := xls.GetRowHeight(Row) / TFlxConsts.RowMult;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetRowHeight\(Integer, Integer, Boolean\)
Returns the current Row height for a given sheet, in Excel internal units\. \(1/20th of a point\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TFlxConsts.RowMult](../TFlxConsts/RowMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetRowHeight(const sheet: Integer; const row: Integer; const HiddenIsZero: Boolean): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where to look for the height\.|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**HiddenIsZero**|Boolean|If true, the height returned for a hidden row will be 0 and not its real height\.|


## Returns

Row height in internal Excel units\.\(1/20th of a point\)

## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RowHeightInPixels := xls.GetRowHeight(Row) / TFlxConsts.RowMult;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

