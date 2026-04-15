---
uid: TSVGBlip
description: TSVGBlip
---

# TSVGBlip Record

Contains the data of an SVG image, when the blip is of SVG type\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TSVGBlip = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(TBytes, Boolean\)](Create.md#tsvgblipcreatetbytes-boolean)<br />  [Create\(TBytes, string, string, Boolean\)](Create.md#tsvgblipcreatetbytes-string-string-boolean)<br />|
|[Clone](Clone.md)|Creates a deep\-copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[ImageFileName](ImageFileName.md)|File name which will be used when saving the file inside the xlsx container\.<br />|
|[ContentType](ContentType.md)|Content type for the image, like "image/jpeg"\.<br />|
|[PictureData](PictureData.md)|Data of the SVG image\. This is normally UTF\-8 encoded\.<br />|
|[Empty](Empty.md)|returns an empty TSVGBlip\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if this svg doesn't have data\.<br />|


