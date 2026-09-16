---
uid: TCmsSigner.SignedAttributes
description: TCmsSigner.SignedAttributes
---

# TCmsSigner\.SignedAttributes Property

Attributes that will be signed together with the document\. Implementations of this class must add them to the PKCS7 signature returned by [GetSignature](GetSignature.md)\. Note that they can be modified after the signer is created, so don't read them until the signature is actually needed\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TCmsSigner/index.md">TCmsSigner</a>.SignedAttributes: <a href="../TCryptographicAttributeObjectCollection/index.md">TCryptographicAttributeObjectCollection</a></code></pre>

## See also

* [TCmsSigner](../TCmsSigner/index.md)

