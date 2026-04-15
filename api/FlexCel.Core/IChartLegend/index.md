---
uid: IChartLegend
description: IChartLegend
---

# IChartLegend Interface

Description of the chart's legend box\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IChartLegend = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Placement](Placement.md)|Placement of the legend inside the chart\. Note that newer Excel versions might report a non\-docked placement even if the legend is docked to a side\. You need to check [CanOverlapWithChart](CanOverlapWithChart.md) to see if the legend is docked, and then look at the side it is to see if it is docked to the left, top, etc\.<br />|
|[CanOverlapWithChart](CanOverlapWithChart.md)|If true, the chart can overlap the legend\. Note that if [Placement](Placement.md) is different from [TChartLegend&#8203;Placement.&#8203;Not&#8203;Docked](../TChartLegendPlacement.md)  then CanOverlapWithChart will be false\. But even if not docked, this value can still be false as newer Excel versions allow you to specify this property on its own\.<br />|
|[Frame](Frame.md)|Line and fill style options for the frame\.<br />|
|[TextOptions](TextOptions.md)|Global font options for the legend labels\.<br />|
|[Position](Position.md)|Coordinates of the legend in percent \(0 to 1\) assuming no margins on the chart area\.<br />If [PositionZeroBased](PositionZeroBased.md) is not null, it must be used instead\. Note that for setting options, this value is ignored and [PositionZeroBased](PositionZeroBased.md) is used instead\.<br />|
|[PositionZeroBased](PositionZeroBased.md)|Coordinates of the legend in percent \(0 to 1\) assuming no margins on the chart area\. If this value is null [Position](Position.md) must be used instead\.<br />|


