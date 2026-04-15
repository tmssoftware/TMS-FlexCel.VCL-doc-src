---
uid: IChartSeries
description: IChartSeries
---

# IChartSeries Interface

The definition for a series, and the values of it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IChartSeries = interface(IInterface);</code></pre>

## Properties

|Name|Description|
|---|---|
|[TitleDefinition](TitleDefinition.md)|Formula or text defining the Series caption\. Start with an "=" sign to enter a formula\.<br />|
|[DataDefinition](DataDefinition.md)|Formula defining the series\. For example, "=A1:A5"\. Start with an "=" sign to enter a formula\.<br />Note that if the Series doesn't have a formula and only values \(for example \{1,2,3\}\), this property will be null and the result will be in [DataValues](DataValues.md)|
|[CategoriesDefinition](CategoriesDefinition.md)|Formula defining the Series Categories \(normally the x Axis\)\. Start with an "=" sign to enter a formula\.<br />Note that if the Series doesn't have a formula and only values, this property will be null and the result will be in [CategoriesValues](CategoriesValues.md)|
|[TitleValue](TitleValue.md)|Evaluated text of the title\.<br />|
|[DataValues](DataValues.md)|Actual values for the series\.<br />|
|[DataValuesHidden](DataValuesHidden.md)|True if all the DataValues are from hidden cells\. When this is true, the length of [DataValues](DataValues.md) is 0\.<br />|
|[CategoriesValues](CategoriesValues.md)|Actual values for the Series Categories \(normally the x Axis\)\. Note that category axis can contain multi\-level labels\. In those cases, CategoriesValues will just report all levels separated by carriage returns\.<br />To see the different levels as an array, use [CategoriesValues&#8203;Array](CategoriesValuesArray.md)|
|[CategoriesValues&#8203;Array](CategoriesValuesArray.md)|Actual values for the Series Categories \(normally the x Axis\)\. This property is similar to [CategoriesValues](CategoriesValues.md) but if the labels have multiple levels, it will return a bi\-dimensional array with one row per level\.<br />|
|[DataFormats](DataFormats.md)|Format on the **cell where the data is**\.<br />So for example if you are charting a range A1:A3, this property will return an array with the numeric format strings for A1, A2 and A3\.<br /><br />This format is applied to the data if the data format for the axis  or the label is null\.<br /><br /><br />Each value in the array holds the format for one data point in the chart\.<br />|
|[CategoriesFormats](CategoriesFormats.md)|Format on the **cell where the data is**\.<br />So for example if you are charting a range A1:A3, this property will return an array with the numeric format strings for A1, A2 and A3\.<br /><br />This format is applied to the data if the data format for the axis  or the label is null\.<br /><br /><br />Each value in the array holds the format for one data point in the chart\.<br />|
|[CategoriesFormats&#8203;Array](CategoriesFormatsArray.md)|Format on the **cell where the data is**\.<br />So for example if you are charting a range A1:A3, this property will return an array with the numeric format strings for A1, A2 and A3\.<br /><br />This format is applied to the data if the data format for the axis  or the label is null\.<br /><br /><br />Each value in the array holds the format for one data point in the chart\.<br />|
|[ChartOptionsIndex](ChartOptionsIndex.md)|Index to the ChartOptions object that applies to this series\. Note that in xlsx charts, this is the number of subchart where the series is\. So when setting series, you don't need to specify the ChartOptionIndex: FlexCel will use the number of subchart no matter what you specify here\.<br />|
|[SeriesIndex](SeriesIndex.md)|Index of this series on the file\.<br />|
|[SeriesNumber](SeriesNumber.md)|Series number as shown on the Legend box\. This might be different from the [SeriesIndex](SeriesIndex.md) if the order of the series is changed\.<br />|
|[Options](Options.md)|Options for this series and their data points\. \-1 means the whole series, and n is options for the n\-point\.<br />|
|[LegendOptions](LegendOptions.md)|Options for the legend entry associated with this series\. \(when legend is showing series\), or with a point on the series\. \(when legend is showing all the entries on series\[0\], for example on pie charts\)|
|[HorizontalErrorBars](HorizontalErrorBars.md)|Returns the horizontal error bar options, if the chart has error bars\. If the chart doesn't have them, then null will be returned\.<br />|
|[VerticalErrorBars](VerticalErrorBars.md)|Returns the vertical error bar options, if the chart has error bars\. If the chart doesn't have them, then null will be returned\.<br />|


