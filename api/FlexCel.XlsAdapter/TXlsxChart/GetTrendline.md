---
uid: TXlsxChart.GetTrendline
description: TXlsxChart.GetTrendline
---

# TXlsxChart\.GetTrendline Method

Gets a trendline for a chart\. This method is only implemented for xlsx charts\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsxChart/index.md">TXlsxChart</a>.GetTrendline(const chartIndex: Integer; const seriesIndex: Integer): <a href="../../FlexCel.Core/IChartTrendline/index.md">IChartTrendline</a>;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**chartIndex**|Integer|Index of the chart \(1 based\)\. Must be bigger than 0 and less\-or\-equal than [IExcelChart.SubchartCount](../../FlexCel.Core/IExcelChart/SubchartCount.md)|
|const|**seriesIndex**|Integer|Index of the series in the chart \(1 based\)\. Must be bigger than 0 and less\-or\-equal than [IExcelChart.SeriesInSubchart](../../FlexCel.Core/IExcelChart/SeriesInSubchart.md)|


## Returns

The trendline definition if there is one, null otherwise\. For xls charts this method will always return null\.

## See also

* [TXlsxChart](../TXlsxChart/index.md)

