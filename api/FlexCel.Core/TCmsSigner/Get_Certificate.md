---
uid: TCmsSigner.Get_Certificate
description: TCmsSigner.Get_Certificate
---

# TCmsSigner\.Get\_Certificate Method

Override this method to return the certificate used to sign the document\. The default implementation returns nil, which means the certificate isn't known until the document is actually signed\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TCmsSigner/index.md">TCmsSigner</a>.Get_Certificate: <a href="../TX509Certificate2/index.md">TX509Certificate2</a>; virtual;</code></pre>

## See also

* [TCmsSigner](../TCmsSigner/index.md)

