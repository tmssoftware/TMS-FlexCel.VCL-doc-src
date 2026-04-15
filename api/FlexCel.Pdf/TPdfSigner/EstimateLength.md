---
uid: TPdfSigner.EstimateLength
description: TPdfSigner.EstimateLength
---

# TPdfSigner\.EstimateLength Method

Returns the estimated length for the data that will be returned in [GetSignature](GetSignature.md)\.
Note that this method will be called **before** finishing the pdf, so you still don't know what the final signature will be\.
You can return a number larger than what [GetSignature](GetSignature.md) will return at the end of the pdf creation, but **never smaller**\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TPdfSigner/index.md">TPdfSigner</a>.EstimateLength: Integer; virtual; abstract;</code></pre>

## See also

* [TPdfSigner](../TPdfSigner/index.md)

