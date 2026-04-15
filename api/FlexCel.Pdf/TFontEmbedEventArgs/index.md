---
uid: TFontEmbedEventArgs
description: TFontEmbedEventArgs
---

# TFontEmbedEventArgs Class

Arguments passed on [TFlexCelPdfExport.OnFontEmbed](../../FlexCel.Render/TFlexCelPdfExport/OnFontEmbed.md)\.
Use this event to specify which fonts to embed and which fonts to ignore\. Note that unicode fonts will be  embedded no matter what you say here\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TFontEmbedEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[InputFont](InputFont.md)|The font for which you need to return the data\.<br />|
|[Embed](Embed.md)|Return true if you want to embed this font, false if you don't want to\. If you don't modify this value, the default will be used\.<br />|


