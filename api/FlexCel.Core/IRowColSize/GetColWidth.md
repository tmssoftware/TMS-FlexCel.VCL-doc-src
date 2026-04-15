---
uid: IRowColSize.GetColWidth
description: IRowColSize.GetColWidth
---

# IRowColSize\.GetColWidth Method

Returns the current Column width, in Excel internal units\. \(Character width of font 0 / 256\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TExcelMetrics.ColMult](../TExcelMetrics/ColMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IRowColSize/index.md">IRowColSize</a>.GetColWidth(const col: Integer; const HiddenIsZero: Boolean): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column Index \(1 based\)|
|const|**HiddenIsZero**|Boolean|If true, the width returned for a hidden column will be 0 and not its real width\.|


## Returns

Column width in internal excel units\.\(Character width of font 0 / 256\)

## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColWidthInPixels := xls.GetColWidth(Col) / TExcelMetrics.ColMult(xls);</span></span>
<span class="line"></span></code></pre>



## See also

* [IRowColSize](../IRowColSize/index.md)

