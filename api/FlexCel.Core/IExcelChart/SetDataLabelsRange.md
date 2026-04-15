---
uid: IExcelChart.SetDataLabelsRange
description: IExcelChart.SetDataLabelsRange
---

# IExcelChart\.SetDataLabelsRange Method

Sets the range of cells for a "Label Contains: " "Value from Cells" option in the labels\.
Note that for this to work, you also need to use the string \[CELLRANGE\] in the label definition\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IExcelChart/index.md">IExcelChart</a>.SetDataLabelsRange(const chartIndex: Integer; const seriesIndex: Integer; const value: <a href="../TDataLabelsRange/index.md">TDataLabelsRange</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**chartIndex**|Integer|Index of the chart \(1 based\)\. Must be bigger than 0 and less\-or\-equal than [SubchartCount](SubchartCount.md)|
|const|**seriesIndex**|Integer|Index of the series in the chart \(1 based\)\. Must be bigger than 0 and less\-or\-equal than [SeriesInSubchart](SeriesInSubchart.md)|
|const|**value**|[TDataLabelsRange](../TDataLabelsRange/index.md)|Value of the range for the series\.|


## See also

* [IExcelChart](../IExcelChart/index.md)

