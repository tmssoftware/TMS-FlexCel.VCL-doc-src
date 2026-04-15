---
uid: IChartTextOptions
description: IChartTextOptions
---

# IChartTextOptions Interface

Options for text inside the chart\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IChartTextOptions = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Font](Font.md)|Font style for the text\.<br />|
|[TextColor](TextColor.md)|Color of the text\.<br />|
|[BackgroundMode](BackgroundMode.md)|Background mode, transparent or opaque\.<br />|
|[HAlign](HAlign.md)|Horizontal alignment for the text\.<br />|
|[VAlign](VAlign.md)|Vertical alignment for the text\.<br />|
|[Rotation](Rotation.md)|Text Rotation in degrees\.<br /><br />When this value is from 0 to 90 then this is the rotation degrees in the up direction\.<br /><br />When this value is from 91 to 180 then this is a rotation in the down direction\. 91 means \-1 degree rotation, 92 means \-2 degrees, and so on until 180 which means \-90 degrees\.<br /><br />255 is vertical text\.<br /><br />Other values are invalid\. If null, then it is not set\.<br />|


