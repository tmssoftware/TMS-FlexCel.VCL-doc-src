---
uid: IDataLabel.PositionXls
description: IDataLabel.PositionXls
---

# IDataLabel.PositionXls Property

Position of the label, assuming margins in the plot area\. This value is only set in xls files, and has different meanings depending on the kind of label:

In titles, x and y are the offset from the chart position in units of 1/4000 of the position\.


In axis titles, x means offset perpendicular to the axis, in units of 1/1000 of the plot\-area bounding box, and y means offset parallel to the axis, in units of 1/1000 of the axis length\.


In data labels for pie charts, x is the offset angle from the default, in degrees clockwise, while y is the radial offset, in units of 1/1000 of the pie radius\.


In data labels for bar and column charts, x is the offset perpendicular to the bar or column, in units of 1/1000 of the plot area, while y is the offset parallel to the bar or column, in units of 1/1000 of the plot area\.


For other charts, x is the horizontal offset from the default position, in units of 1/1000 of the plot area and y is vertical offset from the default position, in units of 1/1000 of the plot area\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IDataLabel/index.md">IDataLabel</a>.PositionXls: <a href="../TXlsChartLabelPosition/index.md">TXlsChartLabelPosition</a></code></pre>

## See also

* [IDataLabel](../IDataLabel/index.md)

