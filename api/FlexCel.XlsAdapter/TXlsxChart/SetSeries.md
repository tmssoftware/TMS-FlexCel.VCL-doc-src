---
uid: TXlsxChart.SetSeries
description: TXlsxChart.SetSeries
---

# TXlsxChart\.SetSeries Method

Sets a Series value\. Note that for xlsx charts, this will change the \*\*data range\*\* and the \*\*options\*\* of the series\. If you only want to change the data range, pass null options to the method\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsxChart/index.md">TXlsxChart</a>.SetSeries(const index: Integer; value: <a href="../../FlexCel.Core/IChartSeries/index.md">IChartSeries</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the series to set\.\(1 based\)|
||**value**|[IChartSeries](../../FlexCel.Core/IChartSeries/index.md)|Series definition\.|


## See also

* [TXlsxChart](../TXlsxChart/index.md)

