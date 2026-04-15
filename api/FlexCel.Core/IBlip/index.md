---
uid: IBlip
description: IBlip
---

# IBlip Interface

Picture and properties used in a Blip fill\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IBlip = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is bigger than this, 0 if both objects are the same, and 1 if obj is smaller than this\.<br />|


## Properties

|Name|Description|
|---|---|
|[CompressionState](CompressionState.md)|Specifies the compression state with which the picture is stored\. This allows the  application to specify the amount of compression that has been applied to a picture\.<br />|
|[PictureData](PictureData.md)|Image data\.<br />|
|[ImageFileName](ImageFileName.md)|File name which will be used when saving the file inside the xlsx container\.<br />|
|[ContentType](ContentType.md)|Content type for the image, like "image/jpeg"\.<br />|
|[BStorePos](BStorePos.md)|Position of the image in the image store\. Internal use\.<br />|
|[SVGBlip](SVGBlip.md)|If the blip contains an SVG image, then the actual data of the SVG image is here\. In this case, PictureData contains a PNG render of the SVG image\.<br />|


