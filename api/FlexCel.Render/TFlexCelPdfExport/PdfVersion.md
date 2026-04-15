---
uid: TFlexCelPdfExport.PdfVersion
description: TFlexCelPdfExport.PdfVersion
---

# TFlexCelPdfExport.PdfVersion Property

Defines the version of pdf being created\. For maximum compatibility you can choose PDF 1\.4\. \(Acrobat 5\.0, but can be opened by any version of Acrobat, even if version less than 1\.4 won't have all the features\)\.
Choosing PDF 1\.6 \(Acrobat 7\) allows for more compression and smaller files, but you'll need Acrobat 7 or newer  to see the files\. Older versions won't be able to open it at all\.


Note that this value might be ignored if you are creating PDFA\-1 \(as it requires PDF1\-4\)\. Also for signing, FlexCel requires PDF 1\.7\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.PdfVersion: <a href="../../FlexCel.Pdf/TPdfVersion.md">TPdfVersion</a></code></pre>

## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

