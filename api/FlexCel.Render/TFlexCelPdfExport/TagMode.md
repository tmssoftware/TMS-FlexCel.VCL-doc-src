---
uid: TFlexCelPdfExport.TagMode
description: TFlexCelPdfExport.TagMode
---

# TFlexCelPdfExport.TagMode Property

If TagMode is full \(the default\), the generated file will be tagged\. Tagged pdfs provide better accesibility support, but the files can be significantly bigger and take a little longer to create\. If you prefer smaller files even if not accessible, turn this option off\. Note that when creating PDF/A files with [PdfType](PdfType.md)  this property defines if the file is PDF/A\-na or PDF/A\-nb\.
This is because PDF/A\-1a and PDF/A\-2a require tagged files, so if this option is true the geneated files will be "a"\.
If this option is false, then the generated files will be "b" which is a less strict standard and doesn't require tagging\.
To reduce file size, you might want to set [PdfVersion](PdfVersion.md) to a value bigger than 1\_4, since this will allow FlexCel to use better compression not available in PDF 1\.4\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.TagMode: <a href="../../FlexCel.Pdf/TTagMode.md">TTagMode</a></code></pre>

## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

