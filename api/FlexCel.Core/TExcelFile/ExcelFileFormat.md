---
uid: TExcelFile.ExcelFileFormat
description: TExcelFile.ExcelFileFormat
---

# TExcelFile.ExcelFileFormat Property

Empty files created by different versions of Excel can have different characteristics\. For example, the default font in an Excel 2003  file is Arial, while the default in 2007 is Calibri, and in 2023 it is Aptos\. This property returns the version of file that is loaded into FlexCel\.
When calling [NewFile\(Integer, TExcelFileFormat\)](NewFile.md#texcelfilenewfileinteger-texcelfileformat) or when opening a new file, FlexCel will update the value of this property\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.ExcelFileFormat: <a href="../TExcelFileFormat.md">TExcelFileFormat</a></code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

