---
uid: IExcelChart.GetSeries
description: IExcelChart.GetSeries
---

# IExcelChart\.GetSeries Method

Returns a series definition\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IExcelChart/index.md">IExcelChart</a>.GetSeries(const index: Integer; const getDefinitions: Boolean; const getValues: Boolean; const getOptions: Boolean): <a href="../IChartSeries/index.md">IChartSeries</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the series you want to return\. \(1 based\)|
|const|**getDefinitions**|Boolean|If false, this method will not return the series formulas, so it will be a little faster\.|
|const|**getValues**|Boolean|If false, this method will not return the series values, so it will be a little faster and use less memory\.|
|const|**getOptions**|Boolean|If false, this method will not return the series options\.|


## Returns

series description\.

## See also

* [IExcelChart](../IExcelChart/index.md)

