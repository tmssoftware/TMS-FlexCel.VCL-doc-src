---
uid: IExcelChart.SetSeriesInSubchart
description: IExcelChart.SetSeriesInSubchart
---

# IExcelChart\.SetSeriesInSubchart Method

Sets a Series value\. Note that for xlsx charts, this will change the \*\*data range\*\* and the \*\*options\*\* of the series\. If you only want to change the data range, pass null options to the method\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IExcelChart/index.md">IExcelChart</a>.SetSeriesInSubchart(const subchart: Integer; const indexInSubchart: Integer; value: <a href="../IChartSeries/index.md">IChartSeries</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**subchart**|Integer|Subchart where we want to set the series\. \(1 based\)|
|const|**indexInSubchart**|Integer|Index of the series to set inside the subchart\.\(1 based\)|
||**value**|[IChartSeries](../IChartSeries/index.md)|Series definition\.|


## See also

* [IExcelChart](../IExcelChart/index.md)

