---
uid: IExcelChart.SetBubbleSeries
description: IExcelChart.SetBubbleSeries
---

# IExcelChart\.SetBubbleSeries Method

Sets a Series value\. Note that for xlsx charts, this will change the \*\*data range\*\* and the \*\*options\*\* of the series\. If you only want to change the data range, pass null options to the method\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IExcelChart/index.md">IExcelChart</a>.SetBubbleSeries(const index: Integer; bubbleSeries: <a href="../IChartBubbleSeries/index.md">IChartBubbleSeries</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the series with the bubbles you want to set\. \(1 based\)|
||**bubbleSeries**|[IChartBubbleSeries](../IChartBubbleSeries/index.md)|The bubble series definition\.|


## See also

* [IExcelChart](../IExcelChart/index.md)

