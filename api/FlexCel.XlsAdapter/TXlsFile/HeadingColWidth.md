---
uid: TXlsFile.HeadingColWidth
description: TXlsFile.HeadingColWidth
---

# TXlsFile.HeadingColWidth Property

Width that will be used by the added column with row numbers when [TExcelFile.PrintHeadings](../../FlexCel.Core/TExcelFile/PrintHeadings.md) is true\.
The default value \(0\) means to use an automatic value which is fine if you don't have too many rows to print\.
A positive value will make the column wider or narrower\. **A negative value will auto\-calculate the width** depending in the  number of rows and normal font of the spreadsheet\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.HeadingColWidth: Double</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)

