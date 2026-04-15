---
uid: IExcelChart
description: IExcelChart
---

# IExcelChart Interface

Information for a chart inside a sheet or an object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IExcelChart = interface(<a href="../IEmbeddedObjects/index.md">IEmbeddedObjects</a>);</code></pre>

## Methods

|Name|Description|
|---|---|
|[SeriesInSubchart](SeriesInSubchart.md)|Returns the number of series on each subchart\. Note that this property only works in xlsx files: In xls files it will always return 0\.<br />|
|[AddSubchart](AddSubchart.md)|Adds a new subchart to the existing chart\. Note that if the current active subchart is empty, this method will not add a new subchart, but replace the empty one\. In that case, [SubchartCount](SubchartCount.md) won't change\.<br /><br />This method only works in xlsx files, not xls\.<br />|
|[SetChartOptions](SetChartOptions.md)|Sets the chart options of a specific subchart inside the chart\. Note that while a chart can have multiple subcharts inside \(for example one pie subchart and one line subchart\), normally there is only one subchart and so the SubchartPos parameter is normally 1\.<br />|
|[GetSeries](GetSeries.md)|Returns a series definition\.<br />|
|[GetSeriesInSubchart](GetSeriesInSubchart.md)|Returns a series definition for a given subchart\. Note: This method only works in xlsx files\.<br />|
|[SetSeries](SetSeries.md)|Sets a Series value\. Note that for xlsx charts, this will change the \*\*data range\*\* and the \*\*options\*\* of the series\. If you only want to change the data range, pass null options to the method\.<br />|
|[SetSeriesInSubchart](SetSeriesInSubchart.md)|Sets a Series value\. Note that for xlsx charts, this will change the \*\*data range\*\* and the \*\*options\*\* of the series\. If you only want to change the data range, pass null options to the method\.<br />|
|[AddSeries](AddSeries.md)|Adds a series to the chart\.<br />|
|[DeleteSeries](DeleteSeries.md)|Deletes the series at position index\.<br />|
|[GetBubbleSeries](GetBubbleSeries.md)|Returns the bubble definition for a series when in a bubble chart\.<br />|
|[SetBubbleSeries](SetBubbleSeries.md)|Sets a Series value\. Note that for xlsx charts, this will change the \*\*data range\*\* and the \*\*options\*\* of the series\. If you only want to change the data range, pass null options to the method\.<br />|
|[GetChartAxis](GetChartAxis.md)|Returns the axis information for this chart\. Note that this might be more than one, if the chart has a secondary axis\.<br />|
|[SetChartAxis](SetChartAxis.md)|Sets the options for either the primary or secondary pair of axis\.<br />|
|[GetChartLegend](GetChartLegend.md)|Information about the Legend of the chart\.<br />|
|[SetChartLegend](SetChartLegend.md)|Sets the legend properties\.<br />|
|[RemoveChartLegend](RemoveChartLegend.md)|Removes the Legend from the chart\.<br />|
|[GetTitle](GetTitle.md)|Returns the title of the chart\.<br />|
|[SetTitle](SetTitle.md)|Sets the title of the chart\. This method is only implemented for xlsx charts\.<br />|
|[GetDataLabels](GetDataLabels.md)|Returns all the labels for the chart\. Note that Axis have their labels defined inside their own definition\.<br />|
|[SetDataLabels](SetDataLabels.md)|Changes the labels for the chart\. You should always get the values with [GetDataLabels](GetDataLabels.md), modify them, and change them back with this method\.<br />|
|[GetDataLabelsRange](GetDataLabelsRange.md)|Returns the range of cells for a "Label Contains: " "Value from Cells" option in the labels\.<br />Note that for this to work, you also need to use the string \[CELLRANGE\] in the label definition\.<br />|
|[SetDataLabelsRange](SetDataLabelsRange.md)|Sets the range of cells for a "Label Contains: " "Value from Cells" option in the labels\.<br />Note that for this to work, you also need to use the string \[CELLRANGE\] in the label definition\.<br />|
|[GetTrendline](GetTrendline.md)|Gets a trendline for a chart\. This method is only implemented for xlsx charts\.<br />|
|[SetTrendline](SetTrendline.md)|Gets a trendline for a chart\. This method is only implemented for xlsx charts\.<br />|
|[GetImageProperties](GetImageProperties.md)|Returns image position and size\.<br />|
|[AddImage](AddImage.md)|**Overloaded<br />**  [AddImage\(TUIImage, IImageProperties\)](AddImage.md#iexcelchartaddimagetuiimage-iimageproperties)<br />  [AddImage\(TBytes, IImageProperties\)](AddImage.md#iexcelchartaddimagetbytes-iimageproperties)<br />  [AddImage\(TStream, IImageProperties\)](AddImage.md#iexcelchartaddimagetstream-iimageproperties)<br />  [AddImage\(string, IImageProperties\)](AddImage.md#iexcelchartaddimagestring-iimageproperties)<br />  [AddImage\(TBytes, TXlsImgType, IImageProperties\)](AddImage.md#iexcelchartaddimagetbytes-txlsimgtype-iimageproperties)<br />  [AddImage\(TStream, TXlsImgType, IImageProperties\)](AddImage.md#iexcelchartaddimagetstream-txlsimgtype-iimageproperties)<br />|
|[DeleteImage](DeleteImage.md)|Deletes the image at position imageIndex\. Note that if the image is grouped, this will remove the full group\.<br />To remove a particular image inside a group, use [IEmbeddedObjects.&#8203;Delete&#8203;Object\(&#8203;&#8203;Integer, string\)](../IEmbeddedObjects/DeleteObject.md#iembeddedobjectsdeleteobjectinteger-string)\.<br />|
|[ClearImage](ClearImage.md)|**Overloaded<br />**  [ClearImage\(Integer\)](ClearImage.md#iexcelchartclearimageinteger)<br />  [ClearImage\(Integer, Boolean, string\)](ClearImage.md#iexcelchartclearimageinteger-boolean-string)<br />|
|[AddAutoShape](AddAutoShape.md)|Adds an autoshape to an existing embedded chart\. Note that the coordinates for the shape are in chart coords, meaning that only row1, row2, col1 and col2 are used, and they represent the percentage in 1/4000 of the coordinate\.<br />So 0 means the top and left of the parent chart, and 4000 means the bottom and right of the parent chart\.<br />|


## Properties

|Name|Description|
|---|---|
|[IsXlsxChart](IsXlsxChart.md)|Returns true if the chart is defined inside an xlsx file instead of xls\. While both charts in xls and xlsx files are mostly compatible, some behaviors can change depending on what type of chart this is\. For example, if the first series in an xls chart is pie, it won't draw gridlines even if the second isn't\. In xlsx charts, if another series is not pie, Excel will draw the gridlines\.<br />|
|[Background](Background.md)|Returns the chart background if there is one defined, or null if there is none\.<br />|
|[DefaultFont](DefaultFont.md)|Returns the default font for all text in the chart that do not have a font defined\.<br />|
|[DefaultLabelFont](DefaultLabelFont.md)|Returns the default font for all labels in the chart that do not have a font defined\.<br />|
|[DefaultAxisFont](DefaultAxisFont.md)|Returns the default font for Axis in the chart that do not have a font defined\.<br />|
|[DefaultAxisTitleFont](DefaultAxisTitleFont.md)|Returns the default font for Axis title in the chart that do not have a font defined\.<br />|
|[DefaultTitleFont](DefaultTitleFont.md)|Returns the default font for Title in the chart that do not have a font defined\.<br />|
|[Style](Style.md)|This is a number between 1 and 48 which defines many standard properties for the chart, like the default line width for the series or the legend\.<br />The default style is 2\.<br />|
|[SubchartCount](SubchartCount.md)|A chart can have multiple subcharts inside: For example one bar chart and one pie chart\.<br />This method returns how many subcharts you have inside the main chart\. Note that this property only works in xlsx files: In xls files it will always return 1\.<br />|
|[ChartOptions](ChartOptions.md)|Returns the type of chart and the options specific for that kind of chart\.<br />There might be more than one ChartOptions returned, since you can mix more than one type of  chart on a simple chart\. \(One for each series\)\. You need to look at the series ChartOptionsIndex to  know to which one it refers\.<br />|
|[PlotArea](PlotArea.md)|Returns or sets the plot area definition for the chart\. Note: Setting the plot area only works in xlsx files\.<br />|
|[PlotEmptyCells](PlotEmptyCells.md)|Defines how null cells will be plotted on the chart\.<br />|
|[ShowDataInHidden&#8203;Rows&#8203;AndCols](ShowDataInHiddenRowsAndCols.md)|Defines if hidden rows and columns will be used when plotting values\.<br />|
|[SeriesCount](SeriesCount.md)|Returns the count of series on this chart\.<br />|
|[ObjectCount](ObjectCount.md)|The number of objects that are embedded inside this chart\.<br />|
|[ImageCount](ImageCount.md)|The number of images in the chart\.<br />|
|[Chart3DOptions](Chart3DOptions.md)|Returns the 3D options for the chart, or null if the chart isn't 3D\.<br />|
|[SideWall](SideWall.md)|The wall next to the y\-axis in a 3D\-chart\.<br />|
|[BackWall](BackWall.md)|The wall at the back of a 3D\-chart|
|[Floor](Floor.md)|The floor in a 3D\-chart\.<br />|


