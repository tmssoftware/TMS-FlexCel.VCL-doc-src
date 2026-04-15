---
uid: TExcelMetrics.ColMultDisplay
description: TExcelMetrics.ColMultDisplay
---

# TExcelMetrics\.ColMultDisplay Method

Multiply by this number to convert the width of a column from GraphicsUnit\.Display units \(1/100 inch\)  to Excel internal units\. Note that the default column width is different, you need to multiply by [DefColWidthAdapt](DefColWidthAdapt.md) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelMetrics/index.md">TExcelMetrics</a>.ColMultDisplay(const Workbook: <a href="../IRowColSize/index.md">IRowColSize</a>): Double; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Workbook**|[IRowColSize](../IRowColSize/index.md)||


## See also

* [TExcelMetrics](../TExcelMetrics/index.md)

