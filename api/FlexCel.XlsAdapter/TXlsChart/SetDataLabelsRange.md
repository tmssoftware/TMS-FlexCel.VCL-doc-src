---
uid: TXlsChart.SetDataLabelsRange
description: TXlsChart.SetDataLabelsRange
---

# TXlsChart\.SetDataLabelsRange Method

Sets the range of cells for a "Label Contains: " "Value from Cells" option in the labels\.
Note that for this to work, you also need to use the string \[CELLRANGE\] in the label definition\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsChart/index.md">TXlsChart</a>.SetDataLabelsRange(const chartIndex: Integer; const seriesIndex: Integer; const value: <a href="../../FlexCel.Core/TDataLabelsRange/index.md">TDataLabelsRange</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**chartIndex**|Integer|Index of the chart \(1 based\)\. Must be bigger than 0 and less\-or\-equal than [IExcelChart.SubchartCount](../../FlexCel.Core/IExcelChart/SubchartCount.md)|
|const|**seriesIndex**|Integer|Index of the series in the chart \(1 based\)\. Must be bigger than 0 and less\-or\-equal than [IExcelChart.SeriesInSubchart](../../FlexCel.Core/IExcelChart/SeriesInSubchart.md)|
|const|**value**|[TDataLabelsRange](../../FlexCel.Core/TDataLabelsRange/index.md)|Value of the range for the series\.|


## See also

* [TXlsChart](../TXlsChart/index.md)

