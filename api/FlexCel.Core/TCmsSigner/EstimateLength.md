---
uid: TCmsSigner.EstimateLength
description: TCmsSigner.EstimateLength
---

# TCmsSigner\.EstimateLength Method

Returns the estimated length for the data that will be returned in [GetSignature](GetSignature.md)\.
Note that this method will be called **before** finishing the pdf, so you still don't know what the final signature will be\.
Return the measured signature size without a safety allowance\. Algorithms such as ECDSA can produce slightly different sizes for different data, so the built\-in pdf signer adds a small allowance of its own on top of what you return here, plus SizeMargin when timestamp settings are supplied\. Keeping this measurement unpadded lets it calculate the timestamp overhead without subtracting that allowance\.

That allowance only covers the variation between two signatures of the same algorithm, not an estimation error: if you can't measure the size exactly, **return a bigger number and never a smaller one**, because a signature that doesn't fit in the space reserved for it is an error\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TCmsSigner/index.md">TCmsSigner</a>.EstimateLength(const aTimestampHandler: TCmsTimestampHandler; const aTimestampHashSize: Integer): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTimestampHandler**|TCmsTimestampHandler|Code that asks a Time Stamping Authority for a timestamp of the signature\.<br />If nil, the signature is not timestamped\.|
|const|**aTimestampHashSize**|Integer|Size in bits of the digest sent to the TSA, 256 or 512\. It is ignored when `aTimestampHandler` is nil\.|


## See also

* [TCmsSigner](../TCmsSigner/index.md)

