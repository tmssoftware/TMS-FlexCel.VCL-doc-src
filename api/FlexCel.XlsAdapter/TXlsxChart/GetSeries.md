---
uid: TXlsxChart.GetSeries
description: TXlsxChart.GetSeries
---

# TXlsxChart\.GetSeries Method

Returns a series definition\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsxChart/index.md">TXlsxChart</a>.GetSeries(const index: Integer; const getDefinitions: Boolean; const getValues: Boolean; const getOptions: Boolean): <a href="../../FlexCel.Core/IChartSeries/index.md">IChartSeries</a>;</code></pre>

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

* [TXlsxChart](../TXlsxChart/index.md)

