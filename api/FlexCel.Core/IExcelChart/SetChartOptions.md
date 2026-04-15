---
uid: IExcelChart.SetChartOptions
description: IExcelChart.SetChartOptions
---

# IExcelChart\.SetChartOptions Method

Sets the chart options of a specific subchart inside the chart\. Note that while a chart can have multiple subcharts inside \(for example one pie subchart and one line subchart\), normally there is only one subchart and so the SubchartPos parameter is normally 1\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IExcelChart/index.md">IExcelChart</a>.SetChartOptions(const subchartPos: Integer; options: <a href="../IChartOptions/index.md">IChartOptions</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**subchartPos**|Integer|Position of the subchart \(1 based\)|
||**options**|[IChartOptions](../IChartOptions/index.md)|Options to set in the subchart\.|


## See also

* [IExcelChart](../IExcelChart/index.md)

