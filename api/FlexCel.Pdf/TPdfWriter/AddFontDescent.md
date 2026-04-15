---
uid: TPdfWriter.AddFontDescent
description: TPdfWriter.AddFontDescent
---

# TPdfWriter.AddFontDescent Property

When false, \(the default\) text base will be at the y coordinate\. For example, DrawString\(\.\.\., y=100,\.\.\.\) will draw a string with its base at 100\. Font descent \(for example the lower part of a "p"\) will be below 100, and the ascent \(the upper part\) will be above\. This is the standard PDF behavior\.
When true, all text will be drawn above the y coordinate\. \(both ascent and descent\)\.
This is the standard GDI\+ behavior, when StringFormat\.LineAlignment=StringAlignment\.Far\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.AddFontDescent: Boolean</code></pre>

## See also

* [TPdfWriter](../TPdfWriter/index.md)

