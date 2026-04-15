---
uid: TPdfWriter.GetFontData
description: TPdfWriter.GetFontData
---

# TPdfWriter.GetFontData Event

Use this event if you want to provide your own font information for embedding for a particular instance\.
Note that if you don't assign this event, [GetFontDataGlobal](GetFontDataGlobal.md) will be used instead\.
If GetFontData and GetFontDataGlobal are not assigned the default method will be used, and this  will try to find the font on the Fonts folder\. To change the font folder, use [GetFontFolder](GetFontFolder.md) event

## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.GetFontData: TGetFontDataEventHandler</code></pre>

## See also

* [TPdfWriter](../TPdfWriter/index.md)

