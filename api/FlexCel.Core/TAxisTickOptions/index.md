---
uid: TAxisTickOptions
description: TAxisTickOptions
---

# TAxisTickOptions Class

Properties for the ticks and labels of an axis\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TAxisTickOptions = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(TTickType, TTickType, TAxisLabelPosition, TBackgroundMode, TDrawingColor, NullableInt32\)](Create.md#taxistickoptionscreatetticktype-tticktype-taxislabelposition-tbackgroundmode-tdrawingcolor-nullableint32)<br />  [Create\(TTickType, TTickType, TAxisLabelPosition, TBackgroundMode, IShapeFill, TDrawingColor, NullableInt32\)](Create.md#taxistickoptionscreatetticktype-tticktype-taxislabelposition-tbackgroundmode-ishapefill-tdrawingcolor-nullableint32)<br />|


## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[MinorTickType](MinorTickType.md)|Major ticks type\.<br />|
|[MajorTickType](MajorTickType.md)|Minor ticks type\.<br />|
|[LabelPosition](LabelPosition.md)|Position of the label relative to the axis\.<br />|
|[BackgroundMode](BackgroundMode.md)|How the background of text will be rendered\.<br />|
|[LabelFill](LabelFill.md)|Background color of the text of labels in this axis\.<br />|
|[LabelColor](LabelColor.md)|Color of the text of labels in this axis\.<br />|
|[Rotation](Rotation.md)|Text Rotation in degrees\.<br /><br />If null, then the rotation will be calculated automatically\.<br />When this value is from 0 to 90 then this is the rotation degrees in the up direction\.<br /><br />When this value is from 91 to 180 then this is a rotation in the down direction\. 91 means \-1 degree rotation, 92 means \-2 degrees, and so on until 180 which means \-90 degrees\.<br /><br />255 is vertical text\.<br /><br />Other values are invalid\.<br />|


