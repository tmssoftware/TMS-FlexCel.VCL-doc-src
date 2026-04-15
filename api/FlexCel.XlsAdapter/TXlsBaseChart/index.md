---
uid: TXlsBaseChart
description: TXlsBaseChart
---

# TXlsBaseChart Class

Implements common functionality in an ExcelChart interface for xls or xlsx charts\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">TXlsBaseChart = class(TRefCountObject, <a href="../../FlexCel.Core/IEmbeddedObjects/index.md">IEmbeddedObjects</a>);</code></pre>

## Fields

|Name|Description|
|---|---|
|[Workbook](Workbook.md)|Workbook holding the chart\.<br />|
|[CurrentSheet](CurrentSheet.md)|Identifier of the current sheet\.<br />|
|[FDefaultFont](FDefaultFont.md)|Default font\.<br />|
|[FDefaultLabelFont](FDefaultLabelFont.md)|Default font for labels\.<br />|
|[FDefaultAxisFont](FDefaultAxisFont.md)|Default font for Axis\.<br />|
|[FDefaultTitleFont](FDefaultTitleFont.md)|Default font for the chart title\.<br />|
|[FDefaultAxis&#8203;Title&#8203;Font](FDefaultAxisTitleFont.md)|Default font for the chart axis title\.<br />|
|[FVerticalFontScaling](FVerticalFontScaling.md)|Vertical font scaling\.<br />|
|[FHorizontalFont&#8203;Scaling](FHorizontalFontScaling.md)|Horizontal font scaling\.<br />|


## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|You cannot create instances of this class\. It must be returned with a call to [TXlsFile.GetChart](../TXlsFile/GetChart.md)|


## Methods

|Name|Description|
|---|---|
|[DoAfterConstruction](DoAfterConstruction.md)|This method will be called after the chart has been created\.<br />|
|[CheckConnected](CheckConnected.md)|Checks if the chart is already loaded\.<br />|
|[CheckRange](CheckRange.md)|Checks if a parameter is in the range\.<br />|
|[CheckRangeObjPath](CheckRangeObjPath.md)|Checks if an ObjPath is in the range\.<br />|
|[CheckRangeObj&#8203;Path&#8203;OrImage&#8203;Index](CheckRangeObjPathOrImageIndex.md)|Checks that a range or path are between bounds\. Internal use\.<br />|
|[GetObjectProperties](GetObjectProperties.md)|Returns information on an object and all of its children\. If the shape doesn't exist, this method returns null\.<br />|
|[HasImageAlternate](HasImageAlternate.md)|Returns true if the image has an alternate representation\. This currently happens only with SVG images, which have a PNG base and an SVG alternate\. If the image has an alternate, you can get the data with [GetImageAlternate](GetImageAlternate.md)|
|[GetImageProperties](GetImageProperties.md)|**Overloaded<br />**  [GetImageProperties\(Integer\)](GetImageProperties.md#txlsbasechartgetimagepropertiesinteger)<br />  [GetImageProperties\(Integer, Boolean, string\)](GetImageProperties.md#txlsbasechartgetimagepropertiesinteger-boolean-string)<br />|
|[AddImage](AddImage.md)|**Overloaded<br />**  [AddImage\(TUIImage, IImageProperties\)](AddImage.md#txlsbasechartaddimagetuiimage-iimageproperties)<br />  [AddImage\(TBytes, IImageProperties\)](AddImage.md#txlsbasechartaddimagetbytes-iimageproperties)<br />  [AddImage\(TStream, IImageProperties\)](AddImage.md#txlsbasechartaddimagetstream-iimageproperties)<br />  [AddImage\(string, IImageProperties\)](AddImage.md#txlsbasechartaddimagestring-iimageproperties)<br />  [AddImage\(TBytes, TXlsImgType, IImageProperties\)](AddImage.md#txlsbasechartaddimagetbytes-txlsimgtype-iimageproperties)<br />  [AddImage\(TStream, TXlsImgType, IImageProperties\)](AddImage.md#txlsbasechartaddimagetstream-txlsimgtype-iimageproperties)<br />|
|[AddImageAlternate](AddImageAlternate.md)|Adds an image to the active sheet\.<br />Currently this method is only needed for SVG images, since SVG images are stored as both PNG and SVG inside the xlsx file\. This method allows you to supply both images\.<br />|
|[DeleteImage](DeleteImage.md)|**Overloaded<br />**  [DeleteImage\(Integer\)](DeleteImage.md#txlsbasechartdeleteimageinteger)<br />  [DeleteImage\(Integer, Boolean, string\)](DeleteImage.md#txlsbasechartdeleteimageinteger-boolean-string)<br />|
|[ClearImage](ClearImage.md)|**Overloaded<br />**  [ClearImage\(Integer\)](ClearImage.md#txlsbasechartclearimageinteger)<br />  [ClearImage\(Integer, Boolean, string\)](ClearImage.md#txlsbasechartclearimageinteger-boolean-string)<br />|
|[AddAutoShape](AddAutoShape.md)|Adds an autoshape to an existing embedded chart\. Note that the coordinates for the shape are in chart coords, meaning that only row1, row2, col1 and col2 are used, and they represent the percentage in 1/4000 of the coordinate\.<br />So 0 means the top and left of the parent chart, and 4000 means the bottom and right of the parent chart\.<br />|
|[SetShapeLinkedCell](SetShapeLinkedCell.md)|Links the shape to a cell, if the shape can be linked\. To unlink the cell, make linkedCell null\.<br />Note that this method applies to shapes like a rectangle or a circle, not to the link of a forms object like a combobox or a radiobutton\.<br />|
|[GetShapeLinkedCell](GetShapeLinkedCell.md)|Returns the cell that is linked to the shape\. If the object isn't linked, this method will return null\.<br />Note that when you change the value in the cell linked to this object, the value of the object will change\.<br />|
|[ImageIndexTo&#8203;Object&#8203;Path](ImageIndexToObjectPath.md)|Returns the absolute object path for an image, given an image index\. Note that this method can be slow if there are many objects in the file\.<br />Whenever possible, prefer the methods that take directly an imageIndex instead of converting the imageIndex to an objectPath\.<br />|
|[SetObjectText](SetObjectText.md)|**Overloaded<br />**  [SetObjectText\(Integer, string, string\)](SetObjectText.md#txlsbasechartsetobjecttextinteger-string-string)<br />  [SetObjectText\(Integer, string, TRichString\)](SetObjectText.md#txlsbasechartsetobjecttextinteger-string-trichstring)<br />  [SetObjectText\(Integer, string, TDrawingRichString\)](SetObjectText.md#txlsbasechartsetobjecttextinteger-string-tdrawingrichstring)<br />|
|[DeleteObject](DeleteObject.md)|**Overloaded<br />**  [DeleteObject\(Integer\)](DeleteObject.md#txlsbasechartdeleteobjectinteger)<br />  [DeleteObject\(Integer, string\)](DeleteObject.md#txlsbasechartdeleteobjectinteger-string)<br />|
|[GetImage](GetImage.md)|Returns an image and its type\.<br />|
|[GetImageAlternate](GetImageAlternate.md)|Returns an image and its type\. Currently this method is the same as [GetImage](GetImage.md) for all images except SVG\.<br />For SVG images, xlsx files store both a PNG and SVG image\. In those cases, this method will return the SVG image\. To get the PNG, call [GetImage](GetImage.md)|


## Properties

|Name|Description|
|---|---|
|[DefaultFont](DefaultFont.md)|Returns the default font for all text in the chart that does not have a font defined\.<br />|
|[DefaultLabelFont](DefaultLabelFont.md)|Returns the default font for all labels in the chart that do not have a font defined\.<br />|
|[DefaultAxisFont](DefaultAxisFont.md)|Returns the default font for the Axis in the chart that do not have a font defined\.<br />|
|[DefaultAxisTitleFont](DefaultAxisTitleFont.md)|Returns the default font for the Axis title in the chart that do not have a font defined\.<br />|
|[DefaultTitleFont](DefaultTitleFont.md)|Returns the default font for the Title in the chart that do not have a font defined\.<br />|
|[ChartOptions](ChartOptions.md)|Returns the type of chart and the options specific for that kind of chart\.<br />There might be more than one ChartOptions returned, since you can mix more than one type of chart on a simple chart\. \(One for each series\)\. You need to look at the series ChartOptionsIndex to know to which one it refers\.<br />|
|[Chart3DOptions](Chart3DOptions.md)|Returns the 3D options for the chart, or null if the chart isn't 3D\.<br />|
|[ImageCount](ImageCount.md)|The number of images in the chart\.<br />|
|[ObjectCount](ObjectCount.md)|The number of objects that are embedded inside this chart\.<br />|


