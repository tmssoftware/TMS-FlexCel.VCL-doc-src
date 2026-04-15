---
uid: TChartSeriesOptions.CreateNoClone
description: TChartSeriesOptions.CreateNoClone
---

# TChartSeriesOptions\.CreateNoClone Method

Creates a new instance of ChartSeriesOptions\. Objects will not be cloned,  and this class will take ownership of them\.
Use this call only if all objects are temporary variables which should be freed later by this class\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TChartSeriesOptions/index.md">TChartSeriesOptions</a>.CreateNoClone(const aPointNumber: Integer; const aFillOptions: <a href="../IChartSeriesFillOptions/index.md">IChartSeriesFillOptions</a>; const aLineOptions: <a href="../IChartSeriesLineOptions/index.md">IChartSeriesLineOptions</a>; const aPieOptions: <a href="../TChartSeriesPieOptions/index.md">TChartSeriesPieOptions</a>; const aMarkerOptions: <a href="../TChartSeriesMarkerOptions/index.md">TChartSeriesMarkerOptions</a>; const aMiscOptions: <a href="../TChartSeriesMiscOptions/index.md">TChartSeriesMiscOptions</a>; const aXlsMode: Boolean): <a href="../TChartSeriesOptions/index.md">TChartSeriesOptions</a>; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPointNumber**|Integer||
|const|**aFillOptions**|[IChartSeries&#8203;Fill&#8203;Options](../IChartSeriesFillOptions/index.md)||
|const|**aLineOptions**|[IChartSeries&#8203;Line&#8203;Options](../IChartSeriesLineOptions/index.md)||
|const|**aPieOptions**|[TChartSeries&#8203;PieOptions](../TChartSeriesPieOptions/index.md)||
|const|**aMarkerOptions**|[TChartSeries&#8203;Marker&#8203;Options](../TChartSeriesMarkerOptions/index.md)||
|const|**aMiscOptions**|[TChartSeries&#8203;Misc&#8203;Options](../TChartSeriesMiscOptions/index.md)||
|const|**aXlsMode**|Boolean||


## See also

* [TChartSeriesOptions](../TChartSeriesOptions/index.md)

