---
uid: TPdfWriter.OnFontEmbedGlobal
description: TPdfWriter.OnFontEmbedGlobal
---

# TPdfWriter.OnFontEmbedGlobal Event

Use this event if you want to manually specify which fonts to embed into the pdf document for the full application\.
Note that if you assign [OnFontEmbed](OnFontEmbed.md) for a particular object instance it will be used instead\.
**Important:** This event isn't thread safe or guarded by any lock\. You should set it once when your application starts and never modify it\. For changing a particular instance, use [OnFontEmbed](OnFontEmbed.md) instead\. If you aren't sure, use [OnFontEmbed](OnFontEmbed.md)

## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.OnFontEmbedGlobal: TFontEmbedEventHandler</code></pre>

## See also

* [TPdfWriter](../TPdfWriter/index.md)

