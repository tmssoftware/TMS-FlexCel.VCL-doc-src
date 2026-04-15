---
uid: TExcelMetrics.ColMult
description: TExcelMetrics.ColMult
---

# TExcelMetrics\.ColMult Method

Multiply by this number to convert the width of a column from resolution\-independent\-pixels \(1/96 of an inch\) to excel internal units\.
Note that the default column width is different, you need to multiply by [DefColWidthAdapt](DefColWidthAdapt.md) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelMetrics/index.md">TExcelMetrics</a>.ColMult(const Workbook: <a href="../IRowColSize/index.md">IRowColSize</a>): Double; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Workbook**|[IRowColSize](../IRowColSize/index.md)||


## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColWidthInPixels := xls.GetColWidth(Col) / TExcelMetrics.ColMult(xls);</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelMetrics](../TExcelMetrics/index.md)

