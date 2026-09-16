---
uid: TPdfSignerFactory.SubFilter
description: TPdfSignerFactory.SubFilter
---

# TPdfSignerFactory\.SubFilter Property

Format of the signatures returned by the [TPdfSigner](../TPdfSigner/index.md) instances this factory creates\. It is written to the "SubFilter" entry of the pdf signature dictionary\. The default implementation returns [TPdfSignatureSubFilter.AdbePkcs7Detached](../TPdfSignatureSubFilter.md); override it if your signer creates CAdES signatures\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfSignerFactory/index.md">TPdfSignerFactory</a>.SubFilter: <a href="../TPdfSignatureSubFilter.md">TPdfSignatureSubFilter</a></code></pre>

## See also

* [TPdfSignerFactory](../TPdfSignerFactory/index.md)

