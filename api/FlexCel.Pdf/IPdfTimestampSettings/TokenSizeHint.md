---
uid: IPdfTimestampSettings.TokenSizeHint
description: IPdfTimestampSettings.TokenSizeHint
---

# IPdfTimestampSettings\.TokenSizeHint Property

Size in bytes of the tokens returned by the TSA, when you already know it\. Set it to avoid the extra call FlexCel needs to measure a sample\. Leave it in 0 to let FlexCel find out by asking for one token\.

Reading it returns the biggest token seen so far, or 0 when no token has been seen yet\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IPdfTimestampSettings/index.md">IPdfTimestampSettings</a>.TokenSizeHint: Integer</code></pre>

## See also

* [IPdfTimestampSettings](../IPdfTimestampSettings/index.md)

