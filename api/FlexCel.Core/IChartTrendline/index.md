---
uid: IChartTrendline
description: IChartTrendline
---

# IChartTrendline Interface

This class holds a definition for a trendline\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IChartTrendline = interface(IInterface);</code></pre>

## Properties

|Name|Description|
|---|---|
|[Name](Name.md)|Name for the trendline\. Make it null to make it automatic\.<br />|
|[LineOptions](LineOptions.md)|Properties of the line, like the color or width\.<br />|
|[TrendlineType](TrendlineType.md)|Type of trendline\.<br />|
|[Order](Order.md)|Integer between 2 and 6 indicating the order of the polynomial\. This property only applies if the [TrendlineType](TrendlineType.md) is [TChartTrendline&#8203;Type.&#8203;Polynomial](../TChartTrendlineType.md)\.<br />|
|[Period](Period.md)|Period for the moving average\. This property only applies if the [TrendlineType](TrendlineType.md) is [TChartTrendline&#8203;Type.&#8203;Moving&#8203;Average](../TChartTrendlineType.md)\.<br />|
|[Forward](Forward.md)|The number of categories \(or units on a scatter chart\) that the trendline extends **after** the data for the series\.<br />This number must be bigger or equal to 0|
|[Backward](Backward.md)|The number of categories \(or units on a scatter chart\) that the trendline extends **before** the data for the series\.<br />If the chart is not scattered, this value must be 0 or 0\.5\.<br />|
|[Intercept](Intercept.md)|This property sets where the trendline crosses the x\-axis\. If null, the crossing point will be automatically calculated\.<br />Only applies for see cref=&#8203;"Trendline&#8203;Type"&#8203;/> of [TChartTrendline&#8203;Type.&#8203;Exponential](../TChartTrendlineType.md), [TChartTrendline&#8203;Type.&#8203;Linear](../TChartTrendlineType.md) or [TChartTrendline&#8203;Type.&#8203;Polynomial](../TChartTrendlineType.md)|
|[DisplayEquation](DisplayEquation.md)|Determines if the trendline equation is displayed on the chart\.<br />|
|[DisplayRSquared](DisplayRSquared.md)|Determines if the value of R\-squared is displayed on the chart\.<br />|
|[LineLabel](LineLabel.md)|Determines if the value of R\-squared is displayed on the chart\.<br />|


