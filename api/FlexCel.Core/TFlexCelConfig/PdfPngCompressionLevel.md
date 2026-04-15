---
uid: TFlexCelConfig.PdfPngCompressionLevel
description: TFlexCelConfig.PdfPngCompressionLevel
---

# TFlexCelConfig.PdfPngCompressionLevel Property

Zip compression level when creating pdf files or re encoding png images\.
Pds and Png files are zip files, and you can compress more or less by trading speed for file size\. The faster you can create the file, the bigger the pdf and png files created will be\.
Normally using compression levels more than default is not worth it, since the files will take a lot longer to be created, and the size reduction will be very small\.


## Remarks

Requires \.NET 4\.5 or newer\. In older \.NET versions it has no effect and compression is always default\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelConfig/index.md">TFlexCelConfig</a>.PdfPngCompressionLevel: <a href="../TCompressionLevel.md">TCompressionLevel</a></code></pre>

## See also

* [TFlexCelConfig](../TFlexCelConfig/index.md)

