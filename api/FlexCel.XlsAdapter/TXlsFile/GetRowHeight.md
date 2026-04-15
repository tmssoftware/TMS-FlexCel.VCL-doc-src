---
uid: TXlsFile.GetRowHeight
description: TXlsFile.GetRowHeight
---

# TXlsFile\.GetRowHeight Method

## Overloads

* [TXlsFile\.GetRowHeight\(Integer\)](#txlsfilegetrowheightinteger)
* [TXlsFile\.GetRowHeight\(Integer, Integer, Boolean\)](#txlsfilegetrowheightinteger-integer-boolean)

# TXlsFile\.GetRowHeight\(Integer\)
Returns the current Row height, in Excel internal units\. \(1/20th of a point\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TFlxConsts.RowMult](../../FlexCel.Core/TFlxConsts/RowMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetRowHeight(const row: Integer): Integer; overload; override;</code></pre>

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

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.GetRowHeight\(Integer, Integer, Boolean\)
Returns the current Row height for a given sheet, in Excel internal units\. \(1/20th of a point\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TFlxConsts.RowMult](../../FlexCel.Core/TFlxConsts/RowMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetRowHeight(const sheet: Integer; const row: Integer; const HiddenIsZero: Boolean): Integer; overload; override;</code></pre>

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

* [TXlsFile](../TXlsFile/index.md)

