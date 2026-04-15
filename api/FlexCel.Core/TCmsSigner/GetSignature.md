---
uid: TCmsSigner.GetSignature
description: TCmsSigner.GetSignature
---

# TCmsSigner\.GetSignature Method

This method is called only once at the end of the pdf creation\. It should release all handles and temporary memory used to calculate the data hash, and return a PKCS7 DER\-encoded signature\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TCmsSigner/index.md">TCmsSigner</a>.GetSignature: TBytes; virtual; abstract;</code></pre>

## See also

* [TCmsSigner](../TCmsSigner/index.md)

