---
uid: IPdfTimestampSettings
description: IPdfTimestampSettings
---

# IPdfTimestampSettings Interface

Says how a signature is timestamped, so it is a PAdES B\-T signature instead of a plain B\-B\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">IPdfTimestampSettings = interface(IInterface);</code></pre>

## Properties

|Name|Description|
|---|---|
|[CacheKey](CacheKey.md)|Identifies the TSA [Handler](Handler.md) talks to, so the size of its tokens is measured once for the whole application instead of once per settings instance\. Use a different key for each TSA \(its url is a good key\) and share it between the factories that use that TSA\. When it is empty, the size is shared with every other settings that has no key: as we keep the biggest size seen, that can only reserve more space than the TSA needs, never less\.<br />|
|[Handler](Handler.md)|Code that sends the timestamp request to a TSA and returns its answer\.<br />|
|[HashAlgorithm](HashAlgorithm.md)|Digest used for the message imprint sent to the TSA\. The default is SHA256\.<br />|
|[SizeMargin](SizeMargin.md)|Bytes reserved in the PDF on top of the size we measure, to allow for the difference between one token and the next one\. Increase it if you get an "estimated length is too small" error when timestamping\.<br />|
|[TokenSizeHint](TokenSizeHint.md)|Size in bytes of the tokens returned by the TSA, when you already know it\. Set it to avoid the extra call FlexCel needs to measure a sample\. Leave it in 0 to let FlexCel find out by asking for one token\.<br /><br />Reading it returns the biggest token seen so far, or 0 when no token has been seen yet\.<br />|


