---
uid: IExcelChart.ChartOptions
description: IExcelChart.ChartOptions
---

# IExcelChart.ChartOptions Property

Returns the type of chart and the options specific for that kind of chart\.
There might be more than one ChartOptions returned, since you can mix more than one type of  chart on a simple chart\. \(One for each series\)\. You need to look at the series ChartOptionsIndex to  know to which one it refers\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IExcelChart/index.md">IExcelChart</a>.ChartOptions: TArray&lt;<a href="../IChartOptions/index.md">IChartOptions</a>&gt;</code></pre>

## See also

* [IExcelChart](../IExcelChart/index.md)

