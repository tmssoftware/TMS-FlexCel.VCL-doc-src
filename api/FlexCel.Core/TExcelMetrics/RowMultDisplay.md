---
uid: TExcelMetrics.RowMultDisplay
description: TExcelMetrics.RowMultDisplay
---

# TExcelMetrics\.RowMultDisplay Method

Multiply by this number to convert the height of a row from GraphicsUnit\.Display units \(1/100 inch\)  to Excel internal units\.
See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

1 Height unit=1/20 pt\. 1pt=1/72 inch\. \-> 1 Height unit=1/\(72\*20\) inch\. \-> 1inch/100= 72\*20/100= 14\.4 PrintPreview on Excel uses different coordinates than the screen\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelMetrics/index.md">TExcelMetrics</a>.RowMultDisplay(const Workbook: <a href="../IRowColSize/index.md">IRowColSize</a>): Double; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Workbook**|[IRowColSize](../IRowColSize/index.md)||


## See also

* [TExcelMetrics](../TExcelMetrics/index.md)

