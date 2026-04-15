---
uid: TSVGBlip.Create
description: TSVGBlip.Create
---

# TSVGBlip\.Create Method

## Overloads

* [TSVGBlip\.Create\(TBytes, Boolean\)](#tsvgblipcreatetbytes-boolean)
* [TSVGBlip\.Create\(TBytes, string, string, Boolean\)](#tsvgblipcreatetbytes-string-string-boolean)

# TSVGBlip\.Create\(TBytes, Boolean\)
Creates a new TSVGBlip with only the blip data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TSVGBlip/index.md">TSVGBlip</a>.Create(const aPictureData: TBytes; const CloneData: Boolean): <a href="../TSVGBlip/index.md">TSVGBlip</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPictureData**|TBytes|SVG image data\. This is normally utf8\-encoded\.|
|const|**CloneData**|Boolean|If true, aPictureData will be cloned before storing it\.<br />If false, aPictureData will be stored directly and it is your responsibility to not use aPictureData anymore\.|


## See also

* [TSVGBlip](../TSVGBlip/index.md)

# TSVGBlip\.Create\(TBytes, string, string, Boolean\)
Creates a new TSVGBlip\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TSVGBlip/index.md">TSVGBlip</a>.Create(const aPictureData: TBytes; const aImageFileName: string; const aContentType: string; const CloneData: Boolean): <a href="../TSVGBlip/index.md">TSVGBlip</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPictureData**|TBytes|SVG image data\. This is normally utf8\-encoded\.|
|const|**aImageFileName**|string|Filename|
|const|**aContentType**|string|Type of image\. This is a mime type, likely [TStandardMimeType.Svg](../TStandardMimeType/Svg.md)|
|const|**CloneData**|Boolean|If true, aPictureData will be cloned before storing it\.<br />If false, aPictureData will be stored directly and it is your responsibility to not use aPictureData anymore\.|


## See also

* [TSVGBlip](../TSVGBlip/index.md)

