---
uid: IChartPlotArea
description: IChartPlotArea
---

# IChartPlotArea Interface

Line and fill styles for the Plot Area\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IChartPlotArea = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[ChartFrameOptions](ChartFrameOptions.md)|Line and fill style for this PlotArea\.<br />|
|[Position](Position.md)|Position of the plot area in the chart\.<br />|
|[LayoutAsExcel2003](LayoutAsExcel2003.md)|When this property is true, this file was saved with Excel 2003 or older, and the layout of the chart is different\.<br />FlexCel uses this property to correctly render charts saved with Excel versions newer or older than Excel 2003\.<br />Note that for xlsx files this property is always false, but for charts in xls files it depends on what version of  Excel was used to create the file\.<br />|
|[CalculatedPosition](CalculatedPosition.md)|Returns the position that was last calculated by Excel, if that was saved in the file\.<br />Note that only xls files save the last calculated position, so in xlsx files this value will be empty\.<br />|


