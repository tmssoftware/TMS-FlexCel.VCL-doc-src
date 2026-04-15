---
uid: TChartSeriesOptions
description: TChartSeriesOptions
---

# TChartSeriesOptions Class

Options for the whole series or for a data point inside it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TChartSeriesOptions = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[CreateWithClones](CreateWithClones.md)|Creates a new instance of ChartSeriesOptions\. Objects will be cloned, so you can change their values later and they will not Use this call only if all objects are owned by others and you will free them independently\. As this class will clone the objects, it will free the cloned objects, and the original objects will leak if you don't free them on their own\.<br />IF you want this class to take ownership of the objects you pass to it, use [CreateNoClone](CreateNoClone.md) change the value on this class\.<br />|


## Methods

|Name|Description|
|---|---|
|[CreateNoClone](CreateNoClone.md)|Creates a new instance of ChartSeriesOptions\. Objects will not be cloned,  and this class will take ownership of them\.<br />Use this call only if all objects are temporary variables which should be freed later by this class\.<br />|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[PointNumber](PointNumber.md)|Point number where this options apply\. \-1 means that the options apply for the whole series\.<br />|
|[FillOptions](FillOptions.md)|Fill options for the series or point\.<br />|
|[LineOptions](LineOptions.md)|Line options for the series or point\.<br />|
|[PieOptions](PieOptions.md)|If the chart type is pie, options for the pie\. If it is not a pie chart, this value has no meaning\.<br />|
|[MarkerOptions](MarkerOptions.md)|Color and shape of the markers on Line and Scatter charts\.<br />|
|[MiscOptions](MiscOptions.md)|Other options not related to the specific parts\.<br />|
|[XlsxMode](XlsxMode.md)|If true, the chart was created by an xlsx\-capable Excel version \(2007 or newer\) and so has different defaults\.<br />For example, it will have different automatic colors for the series\.<br />|


