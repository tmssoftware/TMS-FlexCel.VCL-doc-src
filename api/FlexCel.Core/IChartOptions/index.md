---
uid: IChartOptions
description: IChartOptions
---

# IChartOptions Interface

Base class for options specific to the type of chart\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IChartOptions = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[CompareTo](CompareTo.md)|Orders the chart options depending on their z\-order\.<br />|
|[IsStacked](IsStacked.md)|Returns true is the chart is stacked, either normally or 100%% stacked\.<br />|


## Properties

|Name|Description|
|---|---|
|[AxisNumber](AxisNumber.md)|Axis where this chart group belongs, 0 is primary, 1 is secondary\. In xlsx files it is not used, since the primary or secondary axis is given by the subchart where the series is\.<br />|
|[ChangeColors&#8203;OnEach&#8203;Series](ChangeColorsOnEachSeries.md)|If false, all series will be the same color\.<br />|
|[ChartType](ChartType.md)|Chart Type\.<br />|
|[DefaultLabel](DefaultLabel.md)|Default label properties for this group of charts\.<br />|
|[SeriesOptions](SeriesOptions.md)|Global options for all the series on this chart group\.<br />|
|[ZOrder](ZOrder.md)|Z\-Order of this chart group, with 0 being the bottom\. Chart groups with lower z\-Order are drawn below the ones with higher ones\.<br />|


