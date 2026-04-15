---
uid: TPartialExportState.SaveBody
description: TPartialExportState.SaveBody
---

# TPartialExportState\.SaveBody Method

Use this method to output the body information on this object to an HTML page\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPartialExportState/index.md">TPartialExportState</a>.SaveBody(const writer: <a href="../../FlexCel.Core/TFlexCelWriter/index.md">TFlexCelWriter</a>; const index: Integer; const relativeImagePath: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**writer**|[TFlexCelWriter](../../FlexCel.Core/TFlexCelWriter/index.md)|Writer where you are going to write the information\.|
|const|**index**|Integer|Index of the part that you wish to write\. It must be 1 \<= index \<= [BodyCount](BodyCount.md)|
|const|**relativeImagePath**|string|Image path relative to the main file where the images will be saved\. Note that this path  **does not apply to normal images\.** This is used for example to save the rotated text as images if this option is enabled\.|


## See also

* [TPartialExportState](../TPartialExportState/index.md)

