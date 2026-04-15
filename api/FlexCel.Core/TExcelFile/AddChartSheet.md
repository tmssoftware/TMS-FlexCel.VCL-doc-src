---
uid: TExcelFile.AddChartSheet
description: TExcelFile.AddChartSheet
---

# TExcelFile\.AddChartSheet Method

Adds a chart sheet to the file\. You can then add series and customize the returned ExcelChart object\.
Note that as this is a chart sheet, the anchor is ignored\.
The ActiveSheet after adding the chart will be set to the newly inserted chart\.

**Important:** This method only works in xlsx files\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddChartSheet(const insertBefore: Integer; const chartType: <a href="../TChartType.md">TChartType</a>; const aChartStyle: <a href="../TChartStyle/index.md">TChartStyle</a>; const roundedCorners: Boolean; const print: Boolean; const isLocked: Boolean): <a href="../IExcelChart/index.md">IExcelChart</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**insertBefore**|Integer|The sheet before which we will insert \(1 based\)\. This might be SheetCount \+ 1, to insert at the end of the Workbook\.|
|const|**chartType**|[TChartType](../TChartType.md)|Kind of chart created\. Note that you can have more than one type of chart in the same chart, so this just sets the base chart type\. You can add other chart types over it\.|
|const|**aChartStyle**|[TChartStyle](../TChartStyle/index.md)|Theme of the chart\.<br /><br />This is a number between 1 and 48 which defines many standard properties for the chart, like the default line width for the series or the legend\.<br />The default style is 2\.<br />|
|const|**roundedCorners**|Boolean|If true, the chart will have rounded corners\.|
|const|**print**|Boolean|True if the chart should be printed\.|
|const|**isLocked**|Boolean|True if the chart is locked\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

