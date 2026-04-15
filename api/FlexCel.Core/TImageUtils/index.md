---
uid: TImageUtils
description: TImageUtils
---

# TImageUtils Record

Utilities for manipulating images\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TImageUtils = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[StripOLEHeader](StripOLEHeader.md)|Access stores images encapsulated on an OLE container\. This function will load an OLE image and try to return the raw image data\.<br />|
|[GetImageType](GetImageType.md)|**Overloaded<br />**  [GetImageType\(TBytes\)](GetImageType.md#timageutilsgetimagetypetbytes)<br />  [GetImageType\(TStream\)](GetImageType.md#timageutilsgetimagetypetstream)<br />  [GetImageType\(TBytes, Integer\)](GetImageType.md#timageutilsgetimagetypetbytes-integer)<br />|
|[GetJPEGOrientation](GetJPEGOrientation.md)|This function returns the orientation specific to a JPEG file\. FlexCel will automatically rotate the images you add with AddImage \(same as Excel does\), but it will not rotate the images you enter in the headers/footers or if you replace an existing image\. In those cases, you can use this method to know if the image needs to be rotated before entering it\.<br />|


