---
uid: TXlsChart.SetTrendline
description: TXlsChart.SetTrendline
---

# TXlsChart\.SetTrendline Method

Gets a trendline for a chart\. This method is only implemented for xlsx charts\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsChart/index.md">TXlsChart</a>.SetTrendline(const chartIndex: Integer; const seriesIndex: Integer; trendline: <a href="../../FlexCel.Core/IChartTrendline/index.md">IChartTrendline</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**chartIndex**|Integer|Index of the chart \(1 based\)\. Must be bigger than 0 and less\-or\-equal than [IExcelChart.SubchartCount](../../FlexCel.Core/IExcelChart/SubchartCount.md)|
|const|**seriesIndex**|Integer|Index of the series in the chart \(1 based\)\. Must be bigger than 0 and less\-or\-equal than [IExcelChart.SeriesInSubchart](../../FlexCel.Core/IExcelChart/SeriesInSubchart.md)|
||**trendline**|[IChartTrendline](../../FlexCel.Core/IChartTrendline/index.md)|Trendline definition\.|


## See also

* [TXlsChart](../TXlsChart/index.md)

