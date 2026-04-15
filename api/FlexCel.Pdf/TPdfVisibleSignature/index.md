---
uid: TPdfVisibleSignature
description: TPdfVisibleSignature
---

# TPdfVisibleSignature Class

Describes a visible signature in a PDF file\. For an invisible signature, see [TPdfSignature](../TPdfSignature/index.md)\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TPdfVisibleSignature = class(<a href="../TPdfSignature/index.md">TPdfSignature</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new visible signature for a PDF file\.<br />|


## Properties

|Name|Description|
|---|---|
|[Page](Page.md)|Page where the signature will go\. \(1 based\)\. Use 0 to place the signature at the last page\.<br />|
|[Rect](Rect.md)|Rectangle where the signature will go in the page\. It is measured in points \(1/72 of an inch\) from the left lower corner of the page\.<br />|
|[ImageData](ImageData.md)|The image that will be shown in the signature as an array of bytes\.<br />|


