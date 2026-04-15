---
uid: TPdfWriter.EmbedColorProfile
description: TPdfWriter.EmbedColorProfile
---

# TPdfWriter.EmbedColorProfile Property

If true, a color profile will be embedded in the generated pdf files\. An embedded color profile can increase the size of the generated file in some kilobytes, and it isn't required or needed, so you'll normally want to  keep this property false\. For PDF/A, it is required, but when you set the PdfType to PDF/A the color profile will always be included anyway, and this property will be ignored\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.EmbedColorProfile: Boolean</code></pre>

## See also

* [TPdfWriter](../TPdfWriter/index.md)

