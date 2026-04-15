---
uid: IChartSeries.DataFormats
description: IChartSeries.DataFormats
---

# IChartSeries.DataFormats Property

Format on the **cell where the data is**\.
So for example if you are charting a range A1:A3, this property will return an array with the numeric format strings for A1, A2 and A3\.

This format is applied to the data if the data format for the axis  or the label is null\.


Each value in the array holds the format for one data point in the chart\.


## Remarks

You can't change this value, since it is the cell format\. To change it, change the cell formats for the data instead\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IChartSeries/index.md">IChartSeries</a>.DataFormats: TArray&lt;string&gt;</code></pre>

## See also

* [IChartSeries](../IChartSeries/index.md)

