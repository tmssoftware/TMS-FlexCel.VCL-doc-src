---
uid: IChartPlotArea.LayoutAsExcel2003
description: IChartPlotArea.LayoutAsExcel2003
---

# IChartPlotArea.LayoutAsExcel2003 Property

When this property is true, this file was saved with Excel 2003 or older, and the layout of the chart is different\.
FlexCel uses this property to correctly render charts saved with Excel versions newer or older than Excel 2003\.
Note that for xlsx files this property is always false, but for charts in xls files it depends on what version of  Excel was used to create the file\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IChartPlotArea/index.md">IChartPlotArea</a>.LayoutAsExcel2003: Boolean</code></pre>

## See also

* [IChartPlotArea](../IChartPlotArea/index.md)

