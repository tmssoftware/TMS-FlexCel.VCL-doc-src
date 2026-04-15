---
uid: THtmlDataUri.GetUriBase64
description: THtmlDataUri.GetUriBase64
---

# THtmlDataUri\.GetUriBase64 Method

Creates a data uri according to the RFC 2397: [http://tools.ietf.org/html/rfc2397](http://tools.ietf.org/html/rfc2397) It will use base64 encoding

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THtmlDataUri/index.md">THtmlDataUri</a>.GetUriBase64(const mimeType: string; const data: TBytes): string; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**mimeType**|string|Mime type of the data\. You can use [TStandardMimeType](../TStandardMimeType/index.md) for common mime types\.|
|const|**data**|TBytes|Data to encode\.|


## See also

* [THtmlDataUri](../THtmlDataUri/index.md)

