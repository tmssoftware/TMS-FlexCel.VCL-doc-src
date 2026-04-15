---
uid: TMimeWriter.AddPartHeader
description: TMimeWriter.AddPartHeader
---

# TMimeWriter\.AddPartHeader Method

Adds the header for a part in a multipart Mime message\. After calling this method, you need to write your data content into the TFlexCelWriter using [WriteQuotedPrintable](WriteQuotedPrintable.md) or [WriteBase64](WriteBase64.md) and after that always call [EndPart](EndPart.md)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TMimeWriter/index.md">TMimeWriter</a>.AddPartHeader(const message: <a href="../TFlexCelWriter/index.md">TFlexCelWriter</a>; const contentType: string; const contentTransferEncoding: <a href="../TContentTransferEncoding.md">TContentTransferEncoding</a>; const contentLocation: TUri; const contentId: string; const encodingName: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**message**|[TFlexCelWriter](../TFlexCelWriter/index.md)|TFlexCelWriter where you are saving the message\.|
|const|**contentType**|string|Type of the header as defined in the MIME standard, e\.g\. "text/plain", "text/html", etc\.|
|const|**contentTransferEncoding**|[TContentTransfer&#8203;Encoding](../TContentTransferEncoding.md)|How the part will be codified\. Use base64 for binary TFlexCelWriter and quotedprintable for text\.|
|const|**contentLocation**|TUri|The location for this resource\. null if you do not want to set a location\.|
|const|**contentId**|string|Content id of the resource, if you want to use it in cid: links\. Null if you do not want to specify a content\-id\. Note that this string will not be escaped by the framework, so make sure it  contains valid characters\. As it needs to be globally unique, normally a GUID can be a good option here\.|
|const|**encodingName**|string|Name for the encoding on this part\. Null means do not write an encoding\. \(for example in binary parts\)|


## See also

* [TMimeWriter](../TMimeWriter/index.md)

