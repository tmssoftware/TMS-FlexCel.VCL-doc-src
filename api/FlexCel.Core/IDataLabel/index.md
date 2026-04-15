---
uid: IDataLabel
description: IDataLabel
---

# IDataLabel Interface

Represents one data label on the chart\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IDataLabel = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[PositionXls](PositionXls.md)|Position of the label, assuming margins in the plot area\. This value is only set in xls files, and has different meanings depending on the kind of label:<br /><br />In titles, x and y are the offset from the chart position in units of 1/4000 of the position\.<br /><br /><br />In axis titles, x means offset perpendicular to the axis, in units of 1/1000 of the plot\-area bounding box, and y means offset parallel to the axis, in units of 1/1000 of the axis length\.<br /><br /><br />In data labels for pie charts, x is the offset angle from the default, in degrees clockwise, while y is the radial offset, in units of 1/1000 of the pie radius\.[...[more]](PositionXls.md)|
|[PositionZeroBased](PositionZeroBased.md)|Coordinates in percent of the chart area\. Different from [PositionXls](PositionXls.md) this value has no margin attached\.<br />In old xls files, this value might not be set\. If set, it should always be used instead of [PositionXls](PositionXls.md)\.<br />Note that for titles and axis titles the height and width is always automatic\. For data labels in xlsx files, you can specify a size\.<br />|
|[TextOptions](TextOptions.md)|Formatting options for this label\.<br />|
|[LabelOptions](LabelOptions.md)|Data options for the label\.<br />|
|[Frame](Frame.md)|Background for the label, if there is one\. Null otherwise\.<br />|
|[LabelValues](LabelValues.md)|A list with the actual values for the label, evaluated from the formula at [LabelDefinition](LabelDefinition.md) IMPORTANT NOTE: The values here only are valid if [LabelOptions](LabelOptions.md) indicates a manual DataType\.<br />The results can contain TDrawingRich&#8203;Strings\.&#8203;<br />|
|[LabelDefinition](LabelDefinition.md)|The formula defining the values on this label\. You can access the actual values of the labels with [LabelValues](LabelValues.md)\.<br />|
|[LinkedTo](LinkedTo.md)|Defines to which object this label is linked\.<br />|
|[SeriesIndex](SeriesIndex.md)|Series number for the series this label displays\. This value only has meaning if [LinkedTo](LinkedTo.md) is TLinkOptions\.&#8203;Data&#8203;Label|
|[DataPointIndex](DataPointIndex.md)|Point index of the point this label displays\.  This value only has meaning if [LinkedTo](LinkedTo.md) is TLinkOptions\.&#8203;Data&#8203;Label and the label is for only one point\. When the label is for the whole series, DataPointIndex is \-1\.<br />|
|[NumberFormat](NumberFormat.md)|Numeric format for this label\.<br />|
|[NumberFormat&#8203;Linked&#8203;ToSource](NumberFormatLinkedToSource.md)|True if the format for the numbers on this label is linked to the format in the cells in the spreadsheet\.<br />|
|[LeaderLines](LeaderLines.md)|True if there are lines from the slices to the labels\. This value only has effect in the default label for the series, since you can't individually set leader lines\.<br />|
|[LeaderLineStyle](LeaderLineStyle.md)|Line style for the leader lines, only has meaning if [LeaderLines](LeaderLines.md) is true\.<br />|
|[EnclosingRect](EnclosingRect.md)|Calculated rectangle enclosing the label at zero rotation\. The default value is empty unless you manually set it\.<br />|
|[EnclosingRect&#8203;Rotation](EnclosingRectRotation.md)|The calculated angle in degrees to rotate [EnclosingRect](EnclosingRect.md)\. The default value is empty unless you manually set it\.<br />|


