---
uid: TChartPlotAreaPosition
description: TChartPlotAreaPosition
---

# TChartPlotAreaPosition Record

Defines the rectangle where a chart element is positioned\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TChartPlotAreaPosition = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new plot area position\.<br />|


## Properties

|Name|Description|
|---|---|
|[IsAutomatic](IsAutomatic.md)|If true, then the rectangle is calculated on the fly, and the value of [Rectangle](Rectangle.md) has no meaning\.<br />|
|[Rectangle](Rectangle.md)|Rectangle where the element is\. If [IsAutomatic](IsAutomatic.md) is true, this rectangle has no meaning\.<br />Otherwise, the actual value of the coordinates of the rectangle depend on [LayoutTarget](LayoutTarget.md)\.<br />|
|[LayoutTarget](LayoutTarget.md)|What the [Rectangle](Rectangle.md) means\.<br />|
|[RectangleStarts&#8203;AtZero](RectangleStartsAtZero.md)|In Excel 2003 or older, there is a margin around the plot area where no data can go\.<br />So, a [Rectangle](Rectangle.md) left of 0, meant to the start of the plot area \+ the margin\.<br />After Excel 2007 there is no margin anymore, and so you can place the plotarea at the actual 0 coordinates\.<br />If this property is false, it means the file was last saved by Excel 2003 and [Rectangle](Rectangle.md) includes margins\.<br />|


