---
uid: TDrawingConditionalFormatDataBar
description: TDrawingConditionalFormatDataBar
---

# TDrawingConditionalFormatDataBar Record

Defines the characteristics of a conditional format data bar which is going to be rendered on the screen or to a file\.
It is used for exporting xls/x files to drawings or pdf\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingConditionalFormatDataBar = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new struct and initialized the data\.<br />|


## Properties

|Name|Description|
|---|---|
|[HasDataBar](HasDataBar.md)|If false, the cell doesn't have a databar defined\.<br />|
|[HideValues](HideValues.md)|If true, the contents of the cell won't be displayed\.<br />|
|[Rectangle](Rectangle.md)|Rectangle for the databar, relative to the cell rectangle\. 0 means the Left or Top coordinates of the cell, and 1 the Right or Bottom coordinates of the cell\.<br />|
|[FillColor](FillColor.md)|Color that will be used to fill the databar\.<br />|
|[BorderColor](BorderColor.md)|Border color for the databar\. TUIColor\.Empty means no border\.<br />|
|[AxisColor](AxisColor.md)|Color for the axis where the databar crosses 0\. If this is TUIColor\.Empty, no axis should be drawn\.<br />|
|[IsGradient](IsGradient.md)|If true, the fill will be a gradient starting in [FillColor](FillColor.md) and ending in white\.<br />|
|[IsRightToLeft](IsRightToLeft.md)|If true, the bar goes from Right to left\. If  this property is true and there is a fill gradient in the bar, then the white side of the gradient must be at the left\.<br />|


