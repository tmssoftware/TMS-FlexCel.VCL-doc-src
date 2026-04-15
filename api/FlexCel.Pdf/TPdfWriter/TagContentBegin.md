---
uid: TPdfWriter.TagContentBegin
description: TPdfWriter.TagContentBegin
---

# TPdfWriter\.TagContentBegin Method

Marks the start of a content tag inside a stream\. Must be finished with a call to [TagContentEnd](TagContentEnd.md)

## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.TagContentBegin(const tag: string; const mcid: Integer; const atts: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tag**|string|Name of the tag\. It might be "P", "Clip", "Artifact", etc\.|
|const|**mcid**|Integer|Identifier for the tag\. MCID must be unique in each page\. If negative, no MCID will be written: This can be used in artifacts for example\.|
|const|**atts**|string|Attributes other than mcid\. If null or empty, no attributes will be written|


## See also

* [TPdfWriter](../TPdfWriter/index.md)

