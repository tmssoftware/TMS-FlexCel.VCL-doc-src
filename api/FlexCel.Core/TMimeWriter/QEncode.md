---
uid: TMimeWriter.QEncode
description: TMimeWriter.QEncode
---

# TMimeWriter\.QEncode Method

Returns the Q\-encode of a string, used in the MIME Headers\.  //RFC 2047

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TMimeWriter/index.md">TMimeWriter</a>.QEncode(const s: string; const addMetaInfo: <a href="../TQEncodeMetaInfo.md">TQEncodeMetaInfo</a>): string; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**s**|string|String to encode|
|const|**addMetaInfo**|[TQEncodeMetaInfo](../TQEncodeMetaInfo.md)|Defines if to add the string  "=?charset?encoding?" will be appended at the begining, and "?=" at the end\.|


## See also

* [TMimeWriter](../TMimeWriter/index.md)

