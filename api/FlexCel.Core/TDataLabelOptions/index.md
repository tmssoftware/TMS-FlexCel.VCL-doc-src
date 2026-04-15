---
uid: TDataLabelOptions
description: TDataLabelOptions
---

# TDataLabelOptions Class

Options for a data label\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDataLabelOptions = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[AutoColor](AutoColor.md)|True if this label will use automatic coloring, false if the color is user defined\.<br />|
|[ShowLegendKey](ShowLegendKey.md)|If true, the legend key will be shown along with the label\.<br />|
|[ShowDataLabelsRange](ShowDataLabelsRange.md)|If true and this label [DataType](DataType.md) is SeriesInfo, this label will display the values specified in "Value from Cells" \.<br />|
|[ShowSeriesName](ShowSeriesName.md)|If true and this label [DataType](DataType.md) is SeriesInfo, this label will display the Series name\.<br />|
|[ShowCategories](ShowCategories.md)|If true and this label [DataType](DataType.md) is SeriesInfo, this label will display the Categories\.<br />|
|[ShowValues](ShowValues.md)|If true and this label [DataType](DataType.md) is SeriesInfo, this label will display the actual value of the data\.<br />|
|[ShowPercents](ShowPercents.md)|If true and this label [DataType](DataType.md) is SeriesInfo, this label will display the percentage of the total data\. This value only applies to PIE charts\.<br />|
|[ShowBubbles](ShowBubbles.md)|If true and this label [DataType](DataType.md) is SeriesInfo, this label will display the percentage bubble size\. This value only applies to BUBBLE charts\.<br />|
|[Separator](Separator.md)|The separator that will be used to separate labels when they contain more than one value\. \(For example, if the labels contains both the value and the category, they will be separated by this string\)\.<br />|
|[DataType](DataType.md)|Defines which information this label displays\.<br />|
|[Deleted](Deleted.md)|If true, this label has been manually deleted by the user and should not be displayed\.<br />|
|[Position](Position.md)|Where the label is placed\.<br />|
|[CanOverlapWithChart](CanOverlapWithChart.md)|If true, the label is not used when calculating the plot area dimensions\.<br />|


