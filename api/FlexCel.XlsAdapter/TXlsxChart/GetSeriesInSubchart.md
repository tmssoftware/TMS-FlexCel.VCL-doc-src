---
uid: TXlsxChart.GetSeriesInSubchart
description: TXlsxChart.GetSeriesInSubchart
---

# TXlsxChart\.GetSeriesInSubchart Method

Returns a series definition for a given subchart\. Note: This method only works in xlsx files\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsxChart/index.md">TXlsxChart</a>.GetSeriesInSubchart(const subchart: Integer; const indexInSubchart: Integer; const getDefinitions: Boolean; const getValues: Boolean; const getOptions: Boolean): <a href="../../FlexCel.Core/IChartSeries/index.md">IChartSeries</a>;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**subchart**|Integer|Subchart where we want to get the series from\. \(1 based\)|
|const|**indexInSubchart**|Integer|Index of the series you want to return in the given subchart\. \(1 based\)|
|const|**getDefinitions**|Boolean|If false, this method will not return the series formulas, so it will be a little faster\.|
|const|**getValues**|Boolean|If false, this method will not return the series values, so it will be a little faster and use less memory\.|
|const|**getOptions**|Boolean|If false, this method will not return the series options\.|


## Returns

series description\.

## See also

* [TXlsxChart](../TXlsxChart/index.md)

