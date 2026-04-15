---
uid: TFlxConsts.Max_Rows
description: TFlxConsts.Max_Rows
---

# TFlxConsts.Max_Rows Property

Maximum row in the spreadsheet\. \(0 based\)\.
Note that this number is 1 less than the maximum row count, because this value is 0\-based\. You can use [MaxRowCount](MaxRowCount.md) to get the number of columns instead\.

This number might be 65535 if [TExcelFile.ExcelVersion](../TExcelFile/ExcelVersion.md) is TExcelVersion\.v97\_2003 or 1048575 otherwise\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlxConsts/index.md">TFlxConsts</a>.Max_Rows: Integer</code></pre>

## See also

* [TFlxConsts](../TFlxConsts/index.md)

