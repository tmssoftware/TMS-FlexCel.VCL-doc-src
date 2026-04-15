---
uid: TExcelFile.XlsBiffVersion
description: TExcelFile.XlsBiffVersion
---

# TExcelFile.XlsBiffVersion Property

Xls files created by Excel 2007 have additional records that allow the generated file to store characteristics not available in Excel 2003 or older\.
\(Like for example True color for cells instead of 54 colors\)\. When opening an xls file created by Excel 2007 in Excel 2007, Excel will be able to read those values back\.

By default FlexCel will read those extra records and when reading, and identify the file it creates as created by Excel 2007 when writing, so when you open it in Excel 2007 it will read those additional records\.
If for any reason you prefer FlexCel to behave as Excel 2003, saving the files as if they were created by Excel 2003 \(So Excel 2007 will ignore the additional characteristics\), and also stop FlexCel from reading those extra records, just change the value of this property\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.XlsBiffVersion: <a href="../TXlsBiffVersion.md">TXlsBiffVersion</a></code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

