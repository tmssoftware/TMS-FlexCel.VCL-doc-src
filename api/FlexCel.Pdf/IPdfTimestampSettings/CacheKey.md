---
uid: IPdfTimestampSettings.CacheKey
description: IPdfTimestampSettings.CacheKey
---

# IPdfTimestampSettings\.CacheKey Property

Identifies the TSA [Handler](Handler.md) talks to, so the size of its tokens is measured once for the whole application instead of once per settings instance\. Use a different key for each TSA \(its url is a good key\) and share it between the factories that use that TSA\. When it is empty, the size is shared with every other settings that has no key: as we keep the biggest size seen, that can only reserve more space than the TSA needs, never less\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IPdfTimestampSettings/index.md">IPdfTimestampSettings</a>.CacheKey: string</code></pre>

## See also

* [IPdfTimestampSettings](../IPdfTimestampSettings/index.md)

