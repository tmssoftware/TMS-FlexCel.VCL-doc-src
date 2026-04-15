---
uid: TExcelFile.AddChart
description: TExcelFile.AddChart
---

# TExcelFile\.AddChart Method

This method will add a chart to the active sheet\. You can then add series and customize the returned ExcelChart object\.

**Important:** This method only works in xlsx files\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddChart(objProps: <a href="../IShapeProperties/index.md">IShapeProperties</a>; const chartType: <a href="../TChartType.md">TChartType</a>; const aChartStyle: <a href="../TChartStyle/index.md">TChartStyle</a>; const roundedCorners: Boolean): <a href="../IExcelChart/index.md">IExcelChart</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**objProps**|[IShapeProperties](../IShapeProperties/index.md)|Place where the chart will be placed and characteristics like if it is printable or not\.|
|const|**chartType**|[TChartType](../TChartType.md)|Kind of chart created\. Note that you can have more than one type of chart in the same chart, so this just sets the base chart type\. You can add other chart types over it\.|
|const|**aChartStyle**|[TChartStyle](../TChartStyle/index.md)|Theme of the chart\.<br /><br />This is a number between 1 and 48 which defines many standard properties for the chart, like the default line width for the series or the legend\.<br />The default style is 2\.<br />|
|const|**roundedCorners**|Boolean|If true, the chart will have rounded corners\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

