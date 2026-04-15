---
uid: IExcelChart.SetSeries
description: IExcelChart.SetSeries
---

# IExcelChart\.SetSeries Method

Sets a Series value\. Note that for xlsx charts, this will change the \*\*data range\*\* and the \*\*options\*\* of the series\. If you only want to change the data range, pass null options to the method\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IExcelChart/index.md">IExcelChart</a>.SetSeries(const index: Integer; value: <a href="../IChartSeries/index.md">IChartSeries</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the series to set\.\(1 based\)|
||**value**|[IChartSeries](../IChartSeries/index.md)|Series definition\.|


## See also

* [IExcelChart](../IExcelChart/index.md)

