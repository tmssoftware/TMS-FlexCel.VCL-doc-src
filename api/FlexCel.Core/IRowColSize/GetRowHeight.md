---
uid: IRowColSize.GetRowHeight
description: IRowColSize.GetRowHeight
---

# IRowColSize\.GetRowHeight Method

Returns the current Row height, in Excel internal units\. \(1/20th of a point\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TFlxConsts.RowMult](../TFlxConsts/RowMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IRowColSize/index.md">IRowColSize</a>.GetRowHeight(const row: Integer; const HiddenIsZero: Boolean): Integer; virtual; abstract;</code></pre>

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

* [IRowColSize](../IRowColSize/index.md)

