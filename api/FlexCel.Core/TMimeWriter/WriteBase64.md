---
uid: TMimeWriter.WriteBase64
description: TMimeWriter.WriteBase64
---

# TMimeWriter\.WriteBase64 Method

Writes the base64 encoding of a byte array, as defined in RFC 2045 section 6\.8 This method does not keep the state, so all binary data must be supplied at once\.
This method will also correctly split the string at 76 characters\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class procedure <a href="../TMimeWriter/index.md">TMimeWriter</a>.WriteBase64(const Data: <a href="../TFlexCelWriter/index.md">TFlexCelWriter</a>; const s: TBytes); static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Data**|[TFlexCelWriter](../TFlexCelWriter/index.md)|TFlexCelWriter where we will write the data\.|
|const|**s**|TBytes|String to Encode\.|


## See also

* [TMimeWriter](../TMimeWriter/index.md)

