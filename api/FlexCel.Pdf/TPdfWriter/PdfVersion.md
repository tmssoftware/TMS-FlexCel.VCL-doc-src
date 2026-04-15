---
uid: TPdfWriter.PdfVersion
description: TPdfWriter.PdfVersion
---

# TPdfWriter.PdfVersion Property

Defines the version of pdf being created\. For maximum compatibility you can choose PDF 1\.4\. \(Acrobat 5\.0, but can be opened by any version of Acrobat, even if version less than 1\.4 won't have all the features\)\.
Choosing PDF 1\.6 \(Acrobat 7\) allows for more compression and smaller files, but you'll need Acrobat 7 or newer  to see the files\. Older versions won't be able to open it at all\.


Note that this value will be ignored if you are creating PDFA\-1 \(as it requires PDF1\-4\)\. Also for signing, FlexCel requires PDF1\-6\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.PdfVersion: <a href="../TPdfVersion.md">TPdfVersion</a></code></pre>

## See also

* [TPdfWriter](../TPdfWriter/index.md)

