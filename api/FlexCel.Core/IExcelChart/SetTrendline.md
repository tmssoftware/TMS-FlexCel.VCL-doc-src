---
uid: IExcelChart.SetTrendline
description: IExcelChart.SetTrendline
---

# IExcelChart\.SetTrendline Method

Gets a trendline for a chart\. This method is only implemented for xlsx charts\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IExcelChart/index.md">IExcelChart</a>.SetTrendline(const chartIndex: Integer; const seriesIndex: Integer; trendline: <a href="../IChartTrendline/index.md">IChartTrendline</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**chartIndex**|Integer|Index of the chart \(1 based\)\. Must be bigger than 0 and less\-or\-equal than [SubchartCount](SubchartCount.md)|
|const|**seriesIndex**|Integer|Index of the series in the chart \(1 based\)\. Must be bigger than 0 and less\-or\-equal than [SeriesInSubchart](SeriesInSubchart.md)|
||**trendline**|[IChartTrendline](../IChartTrendline/index.md)|Trendline definition\.|


## See also

* [IExcelChart](../IExcelChart/index.md)

