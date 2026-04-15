---
uid: TGetFontDataEventArgs
description: TGetFontDataEventArgs
---

# TGetFontDataEventArgs Class

Arguments passed on [TFlexCelPdfExport.GetFontData](../../FlexCel.Render/TFlexCelPdfExport/GetFontData.md)\.
Use this event to provide font information for embedding\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TGetFontDataEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[FontData](FontData.md)|Return the full font file as a byte array here\.<br />|
|[Applied](Applied.md)|Set Applied = false if the font is not being processed by the event\.<br />|
|[InputFont](InputFont.md)|The font for which you need to return the data\.<br />|


