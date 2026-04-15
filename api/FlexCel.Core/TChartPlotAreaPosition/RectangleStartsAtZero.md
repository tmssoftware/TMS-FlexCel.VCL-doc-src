---
uid: TChartPlotAreaPosition.RectangleStartsAtZero
description: TChartPlotAreaPosition.RectangleStartsAtZero
---

# TChartPlotAreaPosition.RectangleStartsAtZero Property

In Excel 2003 or older, there is a margin around the plot area where no data can go\.
So, a [Rectangle](Rectangle.md) left of 0, meant to the start of the plot area \+ the margin\.
After Excel 2007 there is no margin anymore, and so you can place the plotarea at the actual 0 coordinates\.
If this property is false, it means the file was last saved by Excel 2003 and [Rectangle](Rectangle.md) includes margins\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TChartPlotAreaPosition/index.md">TChartPlotAreaPosition</a>.RectangleStartsAtZero: Boolean</code></pre>

## See also

* [TChartPlotAreaPosition](../TChartPlotAreaPosition/index.md)

