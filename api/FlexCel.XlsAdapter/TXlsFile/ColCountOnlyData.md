---
uid: TXlsFile.ColCountOnlyData
description: TXlsFile.ColCountOnlyData
---

# TXlsFile.ColCountOnlyData Property

While [TExcelFile.ColCount](../../FlexCel.Core/TExcelFile/ColCount.md) will return the maximum column including both data and formatted columns, this method doesn't include formatted columns, only cells with data, and it is normally what you need to use\.
**Important:** This method includes blank formatted cells\. See [The Maximum Used Column On A Sheet](xref:TheMaximumUsedColumnOnASheet)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.ColCountOnlyData: Integer</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)

