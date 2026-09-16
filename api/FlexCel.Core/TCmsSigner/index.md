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
|[EstimateLength](EstimateLength.md)|Returns the estimated length for the data that will be returned in [GetSignature](GetSignature.md)\.<br />Note that this method will be called **before** finishing the pdf, so you still don't know what the final signature will be\.<br />Return the measured signature size without a safety allowance\. Algorithms such as ECDSA can produce slightly different sizes for different data, so the built\-in pdf signer adds a small allowance of its own on top of what you return here, plus SizeMargin when timestamp settings are supplied\. Keeping this measurement unpadded lets it calculate the timestamp overhead without subtracting that allowance\.<br />[...[more]](EstimateLength.md)|
|[Get\_Certificate](Get_Certificate.md)|Override this method to return the certificate used to sign the document\. The default implementation returns nil, which means the certificate isn't known until the document is actually signed\.<br />|
|[GetSignature](GetSignature.md)|This method is called only once at the end of the pdf creation\. It should release all handles and temporary memory used to calculate the data hash, and return a DER\-encoded signature\.<br />|
|[Write](Write.md)|This method is called each time new data is added to the pdf\. When overwriting this method, use it to incrementally calculate the hash of the data\.<br />|


## Properties

|Name|Description|
|---|---|
|[Certificate](Certificate.md)|Certificate used to sign the document, or nil when it isn't known before signing \(for example when the implementation asks the user to choose a certificate at signing time\)\.<br />|
|[SignedAttributes](SignedAttributes.md)|Attributes that will be signed together with the document\. Implementations of this class must add them to the PKCS7 signature returned by [GetSignature](GetSignature.md)\. Note that they can be modified after the signer is created, so don't read them until the signature is actually needed\.<br />|


