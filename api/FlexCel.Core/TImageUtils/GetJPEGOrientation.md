---
uid: TImageUtils.GetJPEGOrientation
description: TImageUtils.GetJPEGOrientation
---

# TImageUtils\.GetJPEGOrientation Method

This function returns the orientation specific to a JPEG file\. FlexCel will automatically rotate the images you add with AddImage \(same as Excel does\), but it will not rotate the images you enter in the headers/footers or if you replace an existing image\. In those cases, you can use this method to know if the image needs to be rotated before entering it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TImageUtils/index.md">TImageUtils</a>.GetJPEGOrientation(const data: TBytes): <a href="../TJpegOrientation.md">TJpegOrientation</a>; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**data**|TBytes|Image data\.|


## Returns

Orientation of the JPEG file\.

## See also

* [TImageUtils](../TImageUtils/index.md)

