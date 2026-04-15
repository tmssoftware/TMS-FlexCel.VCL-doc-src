---
uid: TMimeWriter.CreateMultiPartMessage
description: TMimeWriter.CreateMultiPartMessage
---

# TMimeWriter\.CreateMultiPartMessage Method

Creates the headers for a multipart MIME file\. This must be the first method to call in order to create a MIME file\.
After this, you need to call [AddPartHeader](AddPartHeader.md) and start adding the parts of the message, and you **always** need to end the message by calling [EndMultiPartMessage](EndMultiPartMessage.md)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TMimeWriter/index.md">TMimeWriter</a>.CreateMultiPartMessage(const message: <a href="../TFlexCelWriter/index.md">TFlexCelWriter</a>; const multipartType: <a href="../TMultipartType.md">TMultipartType</a>; const contentType: string; const contentLocation: TUri);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**message**|[TFlexCelWriter](../TFlexCelWriter/index.md)||
|const|**multipartType**|[TMultipartType](../TMultipartType.md)|Type of multipart for this file\.|
|const|**contentType**|string|Type of the header as defined in the MIME standard, e\.g\. "text/plain", "text/html", etc\. This is the type of the main part on a related message\. Set it to null if there is no main part\.|
|const|**contentLocation**|TUri|The location for the whole mime file\. null if you do not want to set a location\. for this to work in ie/opera, etc, this should be something like "file:///filename\.ext"|


## See also

* [TMimeWriter](../TMimeWriter/index.md)

