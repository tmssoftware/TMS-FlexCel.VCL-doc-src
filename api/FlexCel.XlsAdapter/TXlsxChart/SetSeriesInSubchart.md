---
uid: TXlsxChart.SetSeriesInSubchart
description: TXlsxChart.SetSeriesInSubchart
---

# TXlsxChart\.SetSeriesInSubchart Method

Sets a Series value\. Note that for xlsx charts, this will change the \*\*data range\*\* and the \*\*options\*\* of the series\. If you only want to change the data range, pass null options to the method\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsxChart/index.md">TXlsxChart</a>.SetSeriesInSubchart(const subchart: Integer; const indexInSubchart: Integer; value: <a href="../../FlexCel.Core/IChartSeries/index.md">IChartSeries</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**subchart**|Integer|Subchart where we want to set the series\. \(1 based\)|
|const|**indexInSubchart**|Integer|Index of the series to set inside the subchart\.\(1 based\)|
||**value**|[IChartSeries](../../FlexCel.Core/IChartSeries/index.md)|Series definition\.|


## See also

* [TXlsxChart](../TXlsxChart/index.md)

