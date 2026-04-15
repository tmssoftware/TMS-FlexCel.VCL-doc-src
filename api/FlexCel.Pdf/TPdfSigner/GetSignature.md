---
uid: TPdfSigner.GetSignature
description: TPdfSigner.GetSignature
---

# TPdfSigner\.GetSignature Method

This method is called only once at the end of the pdf creation\. It should release all handles and temporary memory used to calculate the data hash, and return a PKCS7 DER\-encoded signature\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TPdfSigner/index.md">TPdfSigner</a>.GetSignature: TBytes; virtual; abstract;</code></pre>

## See also

* [TPdfSigner](../TPdfSigner/index.md)

