---
uid: TImageUtils.StripOLEHeader
description: TImageUtils.StripOLEHeader
---

# TImageUtils\.StripOLEHeader Method

Access stores images encapsulated on an OLE container\. This function will load an OLE image and try to return the raw image data\.


## Remarks

See Ms kb Q175261

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TImageUtils/index.md">TImageUtils</a>.StripOLEHeader(const data: TBytes): TBytes; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**data**|TBytes|Image in OLE format\.|


## Returns

Image on raw format\.

## See also

* [TImageUtils](../TImageUtils/index.md)

