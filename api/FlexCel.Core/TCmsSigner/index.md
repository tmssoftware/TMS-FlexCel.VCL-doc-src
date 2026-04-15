---
uid: TCmsSigner
description: TCmsSigner
---

# TCmsSigner Class

Represents an abstract class to create a pdf PKCS7 DER encoded signature\.
Descend from this class to create your own SignerFactory implementations\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TCmsSigner = class(TObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Write](Write.md)|This method is called each time new data is added to the pdf\. When overwriting this method, use it to incrementally calculate the hash of the data\.<br />|
|[GetSignature](GetSignature.md)|This method is called only once at the end of the pdf creation\. It should release all handles and temporary memory used to calculate the data hash, and return a PKCS7 DER\-encoded signature\.<br />|
|[EstimateLength](EstimateLength.md)|Returns the estimated length for the data that will be returned in [GetSignature](GetSignature.md)\.<br />Note that this method will be called **before** finishing the pdf, so you still don't know what the final signature will be\.<br />You can return a number larger than what [GetSignature](GetSignature.md) will return at the end of the pdf creation, but **never smaller**\.<br />|


