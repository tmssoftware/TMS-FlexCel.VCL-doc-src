---
uid: TFlxConsts.Max_Columns
description: TFlxConsts.Max_Columns
---

# TFlxConsts.Max_Columns Property

Maximum column in the spreadsheet\. \(0 based\)\.
Note that this number is 1 less than the maximum column count, because this value is 0\-based\. You can use [MaxColCount](MaxColCount.md) to get the number of columns instead\.

This number might be 255 if [TExcelFile.ExcelVersion](../TExcelFile/ExcelVersion.md) is TExcelVersion\.v97\_2003 or 16383 otherwise\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlxConsts/index.md">TFlxConsts</a>.Max_Columns: Integer</code></pre>

## See also

* [TFlxConsts](../TFlxConsts/index.md)

