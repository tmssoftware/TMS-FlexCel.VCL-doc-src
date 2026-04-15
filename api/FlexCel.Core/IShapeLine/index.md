---
uid: IShapeLine
description: IShapeLine
---

# IShapeLine Interface

Contains the information for the line style for an autoshape\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IShapeLine = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|
|[GetLineFill](GetLineFill.md)|This is the color used to draw the line, even if [LineStyle](LineStyle.md) is null|
|[GetWidth](GetWidth.md)|Returns the line width\. If there is a LineStyle this is the Line width, else if it is null it is the Theme line width\.<br />|
|[GetDashing](GetDashing.md)|Returns the line dashing, if there is a LineStyle this is the Line dashing, else if it is null it is the Theme line dashing\.<br />|
|[GetCap](GetCap.md)|Returns the line cap, if there is a LineStyle this is the Line cap, else if it is null it is the Theme line cap\.<br />|
|[GetCompoundLineType](GetCompoundLineType.md)|Returns the line type, if there is a LineStyle this is the Line type, else if it is null it is the Theme line type\.<br />|
|[GetJoin](GetJoin.md)|Returns the line joining, if there is a LineStyle this is the Line join, else if it is null it is the Theme line join\.<br />|
|[GetHeadArrow](GetHeadArrow.md)|Returns the line arrow for the head, if there is a LineStyle this is the Line arrow, else if it is null it is the Theme line arrow\.<br />|
|[GetTailArrow](GetTailArrow.md)|Returns the line arrow for the tail, if there is a LineStyle this is the Line arrow, else if it is null it is the Theme line arrow\.<br />|


## Properties

|Name|Description|
|---|---|
|[HasLine](HasLine.md)|True if the object has a border, false otherwise\.<br />|
|[LineStyle](LineStyle.md)|Line style used to draw the line\. Note that this can be null, and in this case,  a line style from the current theme is used\. If this isn't null, the theme properties are ignored\.<br />|
|[ThemeStyle](ThemeStyle.md)|Theme used to draw the line\. This property has effect only if [LineStyle](LineStyle.md) is null\.<br />|
|[ThemeColor](ThemeColor.md)|Color that will be used instead of the default in the theme, when using a theme to draw the line\.<br />This property has effect only if [LineStyle](LineStyle.md) is null\.<br />|


