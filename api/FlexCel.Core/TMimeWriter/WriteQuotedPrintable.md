---
uid: TMimeWriter.WriteQuotedPrintable
description: TMimeWriter.WriteQuotedPrintable
---

# TMimeWriter\.WriteQuotedPrintable Method

Writes the Quoted Printable encoding of a string, as defined in RFC 2045 section 6\.7 This method keeps state and breaks the line  every time it is longer than 76 characters\.
The state is reset each time [AddPartHeader](AddPartHeader.md) is called\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TMimeWriter/index.md">TMimeWriter</a>.WriteQuotedPrintable(const Data: <a href="../TFlexCelWriter/index.md">TFlexCelWriter</a>; const s: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Data**|[TFlexCelWriter](../TFlexCelWriter/index.md)|TFlexCelWriter where we will write the data\.|
|const|**s**|string|String to Encode\.|


## See also

* [TMimeWriter](../TMimeWriter/index.md)

