---
uid: TXlsxChart.AddSubchart
description: TXlsxChart.AddSubchart
---

# TXlsxChart\.AddSubchart Method

Adds a new subchart to the existing chart\. Note that if the current active subchart is empty, this method will not add a new subchart, but replace the empty one\. In that case, [IExcelChart.SubchartCount](../../FlexCel.Core/IExcelChart/SubchartCount.md) won't change\.

This method only works in xlsx files, not xls\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsxChart/index.md">TXlsxChart</a>.AddSubchart(const chartType: <a href="../../FlexCel.Core/TChartType.md">TChartType</a>; const axisIndex: Integer);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**chartType**|[TChartType](../../FlexCel.Core/TChartType.md)|Type of subchart added\. If it is the same as the current chart type, it won't be added\.|
|const|**axisIndex**|Integer|It can be 0 if the axis of this subchart will be the primary pair of axis, or 1 if they are the secondary pair\.|


## See also

* [TXlsxChart](../TXlsxChart/index.md)

