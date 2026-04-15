---
uid: IObjectProperties
description: IObjectProperties
---

# IObjectProperties Interface

Holds the properties for an object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IObjectProperties = interface(<a href="../IImageProperties/index.md">IImageProperties</a>);</code></pre>

## Methods

|Name|Description|
|---|---|
|[GetRichText](GetRichText.md)|Returns Text as a Rich text instead of a TDrawingRichText\.<br />|


## Properties

|Name|Description|
|---|---|
|[ShapeFill](ShapeFill.md)|Fill style used to fill the background of the comment\. If you are using a solid color, only Indexed colors or RGB are allowed here, if you specify something else, the color will be converted to RGB\. It might be a gradient fill or a texture too\. If null, default fill style will be used\.<br />|
|[InvertedFill](InvertedFill.md)|Fill style used to fill the background of bars in bar charts when the value is negative and "invert negative colors" is true\.<br />|
|[ShapeBorder](ShapeBorder.md)|Line style for the object\.<br />|
|[EffectStyle](EffectStyle.md)|Effects for the object, like inner shadow or glow\.<br />|
|[IsWebAddin](IsWebAddin.md)|Returns true if the object is a web addin\.<br />|


