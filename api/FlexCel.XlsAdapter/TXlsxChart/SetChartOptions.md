---
uid: TXlsxChart.SetChartOptions
description: TXlsxChart.SetChartOptions
---

# TXlsxChart\.SetChartOptions Method

Sets the chart options of a specific subchart inside the chart\. Note that while a chart can have multiple subcharts inside \(for example one pie subchart and one line subchart\), normally there is only one subchart and so the SubchartPos parameter is normally 1\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsxChart/index.md">TXlsxChart</a>.SetChartOptions(const subchartPos: Integer; options: <a href="../../FlexCel.Core/IChartOptions/index.md">IChartOptions</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**subchartPos**|Integer|Position of the subchart \(1 based\)|
||**options**|[IChartOptions](../../FlexCel.Core/IChartOptions/index.md)|Options to set in the subchart\.|


## See also

* [TXlsxChart](../TXlsxChart/index.md)

