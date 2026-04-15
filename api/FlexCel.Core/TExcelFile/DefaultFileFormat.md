---
uid: TExcelFile.DefaultFileFormat
description: TExcelFile.DefaultFileFormat
---

# TExcelFile.DefaultFileFormat Property

Determines the default file format used by Excel when saving a file without specifying one, and when the file format can't be  determined from the extension of the file\. If set to Automatic \(The default\) the file will be saved in the same format it was opened\.
That is, if you opened an xlsx file it will be saved as xlsx\. If you opened an xls file \(or created it with XlsFile\.NewFile\(\)\) it will be saved as xls\.
When this property is automatic, text files will be saved as xls\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.DefaultFileFormat: <a href="../TFileFormats.md">TFileFormats</a></code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

