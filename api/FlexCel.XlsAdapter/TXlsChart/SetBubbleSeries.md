---
uid: TXlsChart.SetBubbleSeries
description: TXlsChart.SetBubbleSeries
---

# TXlsChart\.SetBubbleSeries Method

Sets a Series value\. Note that for xlsx charts, this will change the \*\*data range\*\* and the \*\*options\*\* of the series\. If you only want to change the data range, pass null options to the method\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsChart/index.md">TXlsChart</a>.SetBubbleSeries(const index: Integer; bubbleSeries: <a href="../../FlexCel.Core/IChartBubbleSeries/index.md">IChartBubbleSeries</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the series with the bubbles you want to set\. \(1 based\)|
||**bubbleSeries**|[IChartBubbleSeries](../../FlexCel.Core/IChartBubbleSeries/index.md)|The bubble series definition\.|


## See also

* [TXlsChart](../TXlsChart/index.md)

