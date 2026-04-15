---
uid: TXlsChart.GetBubbleSeries
description: TXlsChart.GetBubbleSeries
---

# TXlsChart\.GetBubbleSeries Method

Returns the bubble definition for a series when in a bubble chart\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsChart/index.md">TXlsChart</a>.GetBubbleSeries(const index: Integer; const getDefinitions: Boolean; const getValues: Boolean): <a href="../../FlexCel.Core/IChartBubbleSeries/index.md">IChartBubbleSeries</a>;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the series with the bubbles you want to return\. \(1 based\)|
|const|**getDefinitions**|Boolean|If false, this method will not return the bubble formulas, so it will be a little faster\.|
|const|**getValues**|Boolean|If false, this method will not return the bubble values, so it will be a little faster and use less memory\.|


## Returns

Bubble descriptions\.

## See also

* [TXlsChart](../TXlsChart/index.md)

