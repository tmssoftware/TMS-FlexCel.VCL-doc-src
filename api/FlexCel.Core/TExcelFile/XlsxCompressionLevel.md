---
uid: TExcelFile.XlsxCompressionLevel
description: TExcelFile.XlsxCompressionLevel
---

# TExcelFile.XlsxCompressionLevel Property

Zip compression level when creating xlsx files\. Xlsx files are zip files, and you can compress more or less by trading speed for file size\. The faster you can create the file, the bigger the xlsx files created will be\.
Excel by default uses "Fastest" compression level and we use "Default"\. Normally using compression levels more than default is not worth it, since the files will take a lot longer to be created, and the size reduction will be very small\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.XlsxCompressionLevel: <a href="../TCompressionLevel.md">TCompressionLevel</a></code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

