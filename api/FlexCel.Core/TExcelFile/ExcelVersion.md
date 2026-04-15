---
uid: TExcelFile.ExcelVersion
description: TExcelFile.ExcelVersion
---

# TExcelFile.ExcelVersion Property

Defines the Excel mode used in this thread\.
Note that while on v2007 \(the default\) you still can make xls 97 spreadsheets, so the only reason to change this setting is if you have any compatibility issues \(for example your formulas depend on a sheet having 65536 rows\)\.
**IMPORTANT: Do NOT change this value after reading a workbook**\. Also, remember that the value is changed for all the reports in all threads\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.ExcelVersion: <a href="../TExcelVersion.md">TExcelVersion</a></code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

