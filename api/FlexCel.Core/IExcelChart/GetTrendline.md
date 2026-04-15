---
uid: IExcelChart.GetTrendline
description: IExcelChart.GetTrendline
---

# IExcelChart\.GetTrendline Method

Gets a trendline for a chart\. This method is only implemented for xlsx charts\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IExcelChart/index.md">IExcelChart</a>.GetTrendline(const chartIndex: Integer; const seriesIndex: Integer): <a href="../IChartTrendline/index.md">IChartTrendline</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**chartIndex**|Integer|Index of the chart \(1 based\)\. Must be bigger than 0 and less\-or\-equal than [SubchartCount](SubchartCount.md)|
|const|**seriesIndex**|Integer|Index of the series in the chart \(1 based\)\. Must be bigger than 0 and less\-or\-equal than [SeriesInSubchart](SeriesInSubchart.md)|


## Returns

The trendline definition if there is one, null otherwise\. For xls charts this method will always return null\.

## See also

* [IExcelChart](../IExcelChart/index.md)

