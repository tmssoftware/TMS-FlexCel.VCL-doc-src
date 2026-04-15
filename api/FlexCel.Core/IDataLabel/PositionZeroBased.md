---
uid: IDataLabel.PositionZeroBased
description: IDataLabel.PositionZeroBased
---

# IDataLabel.PositionZeroBased Property

Coordinates in percent of the chart area\. Different from [PositionXls](PositionXls.md) this value has no margin attached\.
In old xls files, this value might not be set\. If set, it should always be used instead of [PositionXls](PositionXls.md)\.
Note that for titles and axis titles the height and width is always automatic\. For data labels in xlsx files, you can specify a size\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IDataLabel/index.md">IDataLabel</a>.PositionZeroBased: NullableTChartRelativeRectangle</code></pre>

## See also

* [IDataLabel](../IDataLabel/index.md)

