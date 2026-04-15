---
uid: TPdfWriter.GetFontDataGlobal
description: TPdfWriter.GetFontDataGlobal
---

# TPdfWriter.GetFontDataGlobal Event

Use this event if you want to provide your own font information for embedding for the full application\.
Note that if you assign [GetFontData](GetFontData.md) for a particular object instance it will be used instead\.
**Important:** This event isn't thread safe or guarded by any lock\. You should set it once when your application starts and never modify it\. For changing a particular instance, use [GetFontData](GetFontData.md) instead\. If you aren't sure, use [GetFontData](GetFontData.md)

## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.GetFontDataGlobal: TGetFontDataEventHandler</code></pre>

## See also

* [TPdfWriter](../TPdfWriter/index.md)

