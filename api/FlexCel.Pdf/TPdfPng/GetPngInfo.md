---
uid: TPdfPng.GetPngInfo
description: TPdfPng.GetPngInfo
---

# TPdfPng\.GetPngInfo Method

Returns the basic information on a png file\. Null if the file is not PNG\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TPdfPng/index.md">TPdfPng</a>.GetPngInfo(const PngImageData: TStream): <a href="../TPngInformation/index.md">TPngInformation</a>; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**PngImageData**|TStream|Stream with the image data\.|


## Returns

Null if the image is invalid, or the image properties otherwise\.

## See also

* [TPdfPng](../TPdfPng/index.md)

