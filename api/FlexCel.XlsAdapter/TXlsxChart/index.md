---
uid: TXlsxChart
description: TXlsxChart
---

# TXlsxChart Class

Implements an ExcelChart interface for charts in xlsx files\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">TXlsxChart = class(<a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>, <a href="../../FlexCel.Core/IExcelChart/index.md">IExcelChart</a>);</code></pre>

## Methods

|Name|Description|
|---|---|
|[SeriesInSubchart](SeriesInSubchart.md)|Returns the number of series on each subchart\. Note that this property only works in xlsx files: In xls files it will always return 0\.<br />|
|[AddSubchart](AddSubchart.md)|Adds a new subchart to the existing chart\. Note that if the current active subchart is empty, this method will not add a new subchart, but replace the empty one\. In that case, [IExcelChart.&#8203;Subchart&#8203;Count](../../FlexCel.Core/IExcelChart/SubchartCount.md) won't change\.<br /><br />This method only works in xlsx files, not xls\.<br />|
|[SetChartOptions](SetChartOptions.md)|Sets the chart options of a specific subchart inside the chart\. Note that while a chart can have multiple subcharts inside \(for example one pie subchart and one line subchart\), normally there is only one subchart and so the SubchartPos parameter is normally 1\.<br />|
|[AddSeries](AddSeries.md)|Adds a series to the chart\.<br />|
|[DeleteSeries](DeleteSeries.md)|Deletes the series at position index\.<br />|
|[GetSeries](GetSeries.md)|Returns a series definition\.<br />|
|[GetSeriesInSubchart](GetSeriesInSubchart.md)|Returns a series definition for a given subchart\. Note: This method only works in xlsx files\.<br />|
|[SetSeries](SetSeries.md)|Sets a Series value\. Note that for xlsx charts, this will change the \*\*data range\*\* and the \*\*options\*\* of the series\. If you only want to change the data range, pass null options to the method\.<br />|
|[SetSeriesInSubchart](SetSeriesInSubchart.md)|Sets a Series value\. Note that for xlsx charts, this will change the \*\*data range\*\* and the \*\*options\*\* of the series\. If you only want to change the data range, pass null options to the method\.<br />|
|[GetBubbleSeries](GetBubbleSeries.md)|Returns the bubble definition for a series when in a bubble chart\.<br />|
|[SetBubbleSeries](SetBubbleSeries.md)|Sets a Series value\. Note that for xlsx charts, this will change the \*\*data range\*\* and the \*\*options\*\* of the series\. If you only want to change the data range, pass null options to the method\.<br />|
|[GetChartAxis](GetChartAxis.md)|Returns the axis information for this chart\. Note that this might be more than one, if the chart has a secondary axis\.<br />|
|[SetChartAxis](SetChartAxis.md)|Sets the options for either the primary or secondary pair of axis\.<br />|
|[GetDataLabels](GetDataLabels.md)|Returns all the labels for the chart\. Note that Axis have their labels defined inside their own definition\.<br />|
|[SetDataLabels](SetDataLabels.md)|Changes the labels for the chart\. You should always get the values with [IExcelChart.&#8203;Get&#8203;Data&#8203;Labels](../../FlexCel.Core/IExcelChart/GetDataLabels.md), modify them, and change them back with this method\.<br />|
|[GetDataLabelsRange](GetDataLabelsRange.md)|Returns the range of cells for a "Label Contains: " "Value from Cells" option in the labels\.<br />Note that for this to work, you also need to use the string \[CELLRANGE\] in the label definition\.<br />|
|[SetDataLabelsRange](SetDataLabelsRange.md)|Sets the range of cells for a "Label Contains: " "Value from Cells" option in the labels\.<br />Note that for this to work, you also need to use the string \[CELLRANGE\] in the label definition\.<br />|
|[GetTitle](GetTitle.md)|Returns the title of the chart\.<br />|
|[SetTitle](SetTitle.md)|Sets the title of the chart\. This method is only implemented for xlsx charts\.<br />|
|[GetChartLegend](GetChartLegend.md)|Information about the Legend of the chart\.<br />|
|[SetChartLegend](SetChartLegend.md)|Sets the legend properties\.<br />|
|[RemoveChartLegend](RemoveChartLegend.md)|Removes the Legend from the chart\.<br />|
|[GetTrendline](GetTrendline.md)|Gets a trendline for a chart\. This method is only implemented for xlsx charts\.<br />|
|[SetTrendline](SetTrendline.md)|Gets a trendline for a chart\. This method is only implemented for xlsx charts\.<br />|
|[GetObjectProperties](GetObjectProperties.md)|Returns information on an object and all of its children\. If the shape doesn't exist, this method returns null\.<br />|
|[SetObjectText](SetObjectText.md)|**Overloaded<br />**  [SetObjectText\(Integer, string, string\)](SetObjectText.md#txlsxchartsetobjecttextinteger-string-string)<br />  [SetObjectText\(Integer, string, TRichString\)](SetObjectText.md#txlsxchartsetobjecttextinteger-string-trichstring)<br />  [SetObjectText\(Integer, string, TDrawingRichString\)](SetObjectText.md#txlsxchartsetobjecttextinteger-string-tdrawingrichstring)<br />|
|[DeleteObject](DeleteObject.md)|**Overloaded<br />**  [DeleteObject\(Integer\)](DeleteObject.md#txlsxchartdeleteobjectinteger)<br />  [DeleteObject\(Integer, string\)](DeleteObject.md#txlsxchartdeleteobjectinteger-string)<br />|
|[GetImage](GetImage.md)|Returns an image and its type\.<br />|
|[GetImageAlternate](GetImageAlternate.md)|Returns an image and its type\. Currently this method is the same as [TXlsBaseChart.&#8203;Get&#8203;Image](../TXlsBaseChart/GetImage.md) for all images except SVG\.<br />For SVG images, xlsx files store both a PNG and SVG image\. In those cases, this method will return the SVG image\. To get the PNG, call [TXlsBaseChart.&#8203;Get&#8203;Image](../TXlsBaseChart/GetImage.md)|


## Properties

|Name|Description|
|---|---|
|[IsXlsxChart](IsXlsxChart.md)|Returns true if the chart is defined inside an xlsx file instead of xls\. While both charts in xls and xlsx files are mostly compatible, some behaviors can change depending on what type of chart this is\. For example, if the first series in an xls chart is pie, it won't draw gridlines even if the second isn't\. In xlsx charts, if another series is not pie, Excel will draw the gridlines\.<br />|
|[Style](Style.md)|This is a number between 1 and 48 which defines many standard properties for the chart, like the default line width for the series or the legend\.<br />The default style is 2\.<br />|
|[SubchartCount](SubchartCount.md)|A chart can have multiple subcharts inside: For example one bar chart and one pie chart\.<br />This method returns how many subcharts you have inside the main chart\. Note that this property only works in xlsx files: In xls files it will always return 1\.<br />|
|[Background](Background.md)|Options for the background of the full chart\. If this member is null, the options for the Autoshape will be used\.<br />|
|[DefaultFont](DefaultFont.md)|Returns the default font for all text in the chart that do not have a font defined\.<br />|
|[DefaultLabelFont](DefaultLabelFont.md)|Returns the default font for all labels in the chart that do not have a font defined\.<br />|
|[DefaultAxisFont](DefaultAxisFont.md)|Returns the default font for Axis in the chart that do not have a font defined\.<br />|
|[DefaultAxisTitleFont](DefaultAxisTitleFont.md)|Returns the default font for Axis title in the chart that do not have a font defined\.<br />|
|[DefaultTitleFont](DefaultTitleFont.md)|Returns the default font for Title in the chart that do not have a font defined\.<br />|
|[PlotEmptyCells](PlotEmptyCells.md)|Defines how null cells will be plotted on the chart\.<br />|
|[ShowDataInHidden&#8203;Rows&#8203;AndCols](ShowDataInHiddenRowsAndCols.md)|Defines if hidden rows and columns will be used when plotting values\.<br />|
|[PlotArea](PlotArea.md)|Returns or sets the plot area definition for the chart\. Note: Setting the plot area only works in xlsx files\.<br />|
|[Chart3DOptions](Chart3DOptions.md)|Returns the 3D options for the chart, or null if the chart isn't 3D\.<br />|
|[Floor](Floor.md)|The floor in a 3D\-chart\.<br />|
|[SideWall](SideWall.md)|The wall next to the y\-axis in a 3D\-chart\.<br />|
|[BackWall](BackWall.md)|The wall at the back of a 3D\-chart|
|[SeriesCount](SeriesCount.md)|Returns the count of series on this chart\.<br />|
|[ObjectCount](ObjectCount.md)|The number of objects that are embedded inside this chart\.<br />|


