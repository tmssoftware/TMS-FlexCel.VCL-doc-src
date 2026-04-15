---
uid: TXlsxChart.IsXlsxChart
description: TXlsxChart.IsXlsxChart
---

# TXlsxChart.IsXlsxChart Property

Returns true if the chart is defined inside an xlsx file instead of xls\. While both charts in xls and xlsx files are mostly compatible, some behaviors can change depending on what type of chart this is\. For example, if the first series in an xls chart is pie, it won't draw gridlines even if the second isn't\. In xlsx charts, if another series is not pie, Excel will draw the gridlines\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsxChart/index.md">TXlsxChart</a>.IsXlsxChart: Boolean</code></pre>

## See also

* [TXlsxChart](../TXlsxChart/index.md)

