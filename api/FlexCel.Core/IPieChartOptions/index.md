---
uid: IPieChartOptions
description: IPieChartOptions
---

# IPieChartOptions Interface

Options specific for a Pie chart\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IPieChartOptions = interface(<a href="../IChartOptions/index.md">IChartOptions</a>);</code></pre>

## Properties

|Name|Description|
|---|---|
|[FirstSliceAngle](FirstSliceAngle.md)|Angle of the first slice in degrees\. It can go from 0 to 359\.<br />|
|[DoughnutRadius](DoughnutRadius.md)|Radius of the center of the doughnut in Percent\. 0 Means a Pie without hole\.<br />Note that in xls charts, 0 means a Pie chart\. In xlsx, 0 still means a doughnut chart, but without hole in the middle\. It is not possible to have a doughnut chart without hole in xls\.<br />|
|[IsDoughnut](IsDoughnut.md)|Returns true if the chart is a doughnut chart instead of a pie chart\. In xls charts, a pie chart is just defined as [DoughnutRadius](DoughnutRadius.md) = 0, but in xlsx you can have doughnut charts with [DoughnutRadius](DoughnutRadius.md) = 0\.<br />|
|[HasShadow](HasShadow.md)|True if the chart lines have shadows\.<br />|


