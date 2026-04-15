---
uid: TGetImageDataEventArgs
description: TGetImageDataEventArgs
---

# TGetImageDataEventArgs Class

Arguments passed on [TFlexCelReport.GetImageData](../TFlexCelReport/GetImageData.md)

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TGetImageDataEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[DataFile](DataFile.md)|The file with the report data\.<br />|
|[ImageName](ImageName.md)|The name of the image on the Excel sheet\. Use it to identify it\.<br />|
|[ImageData](ImageData.md)|The data of the image\. You can modify it to return another image format\.<br />|
|[Height](Height.md)|The height of the image in pixels\. Change it to resize the image\.<br />|
|[Width](Width.md)|The width of the image in pixels\. Change it to resize the image\.<br />|


