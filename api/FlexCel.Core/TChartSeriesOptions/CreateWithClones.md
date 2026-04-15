---
uid: TChartSeriesOptions.CreateWithClones
description: TChartSeriesOptions.CreateWithClones
---

# TChartSeriesOptions\.CreateWithClones Constructor

Creates a new instance of ChartSeriesOptions\. Objects will be cloned, so you can change their values later and they will not Use this call only if all objects are owned by others and you will free them independently\. As this class will clone the objects, it will free the cloned objects, and the original objects will leak if you don't free them on their own\.
IF you want this class to take ownership of the objects you pass to it, use [CreateNoClone](CreateNoClone.md) change the value on this class\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TChartSeriesOptions/index.md">TChartSeriesOptions</a>.CreateWithClones(const aPointNumber: Integer; aFillOptions: <a href="../IChartSeriesFillOptions/index.md">IChartSeriesFillOptions</a>; aLineOptions: <a href="../IChartSeriesLineOptions/index.md">IChartSeriesLineOptions</a>; const aPieOptions: <a href="../TChartSeriesPieOptions/index.md">TChartSeriesPieOptions</a>; const aMarkerOptions: <a href="../TChartSeriesMarkerOptions/index.md">TChartSeriesMarkerOptions</a>; const aMiscOptions: <a href="../TChartSeriesMiscOptions/index.md">TChartSeriesMiscOptions</a>; const aXlsMode: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPointNumber**|Integer|Point number where this options apply\. \-1 means that the options apply for the whole series\.|
||**aFillOptions**|[IChartSeries&#8203;Fill&#8203;Options](../IChartSeriesFillOptions/index.md)|Fill options for the series or point\.|
||**aLineOptions**|[IChartSeries&#8203;Line&#8203;Options](../IChartSeriesLineOptions/index.md)|Line options for the series or point\.|
|const|**aPieOptions**|[TChartSeries&#8203;PieOptions](../TChartSeriesPieOptions/index.md)|If the chart type is pie, options for the pie\. If it is not a pie chart, this value has no meaning\.|
|const|**aMarkerOptions**|[TChartSeries&#8203;Marker&#8203;Options](../TChartSeriesMarkerOptions/index.md)|Color and shape of the markers on Line and Scatter charts\.|
|const|**aMiscOptions**|[TChartSeries&#8203;Misc&#8203;Options](../TChartSeriesMiscOptions/index.md)|Misc Options\.|
|const|**aXlsMode**|Boolean|If true, this is a xlsx chart, which has different automatic colors, etc\.|


## See also

* [TChartSeriesOptions](../TChartSeriesOptions/index.md)

