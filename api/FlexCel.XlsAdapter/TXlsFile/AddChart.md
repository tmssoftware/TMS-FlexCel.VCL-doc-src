---
uid: TXlsFile.AddChart
description: TXlsFile.AddChart
---

# TXlsFile\.AddChart Method

This method will add a chart to the active sheet\. You can then add series and customize the returned ExcelChart object\.

**Important:** This method only works in xlsx files\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.AddChart(objProps: <a href="../../FlexCel.Core/IShapeProperties/index.md">IShapeProperties</a>; const chartType: <a href="../../FlexCel.Core/TChartType.md">TChartType</a>; const aChartStyle: <a href="../../FlexCel.Core/TChartStyle/index.md">TChartStyle</a>; const roundedCorners: Boolean): <a href="../../FlexCel.Core/IExcelChart/index.md">IExcelChart</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**objProps**|[IShapeProperties](../../FlexCel.Core/IShapeProperties/index.md)|Place where the chart will be placed and characteristics like if it is printable or not\.|
|const|**chartType**|[TChartType](../../FlexCel.Core/TChartType.md)|Kind of chart created\. Note that you can have more than one type of chart in the same chart, so this just sets the base chart type\. You can add other chart types over it\.|
|const|**aChartStyle**|[TChartStyle](../../FlexCel.Core/TChartStyle/index.md)|Theme of the chart\.<br /><br />This is a number between 1 and 48 which defines many standard properties for the chart, like the default line width for the series or the legend\.<br />The default style is 2\.<br />|
|const|**roundedCorners**|Boolean|If true, the chart will have rounded corners\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

