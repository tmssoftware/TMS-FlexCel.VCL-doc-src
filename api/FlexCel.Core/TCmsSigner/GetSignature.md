---
uid: TCmsSigner.GetSignature
description: TCmsSigner.GetSignature
---

# TCmsSigner\.GetSignature Method

This method is called only once at the end of the pdf creation\. It should release all handles and temporary memory used to calculate the data hash, and return a DER\-encoded signature\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TCmsSigner/index.md">TCmsSigner</a>.GetSignature(const aTimestampHandler: TCmsTimestampHandler; const aTimestampHashSize: Integer): TBytes; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTimestampHandler**|TCmsTimestampHandler|Code that asks a Time Stamping Authority for a timestamp of the signature\.<br />If nil, the signature won't be timestamped\.|
|const|**aTimestampHashSize**|Integer|Size in bits of the digest sent to the TSA, 256 or 512\. It is ignored when `aTimestampHandler` is nil\.|


## Returns

A DER\-encoded signature\.

## See also

* [TCmsSigner](../TCmsSigner/index.md)

