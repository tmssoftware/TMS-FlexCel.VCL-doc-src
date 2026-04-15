---
uid: TCustomizeChartEventArgs
description: TCustomizeChartEventArgs
---

# TCustomizeChartEventArgs Class

Arguments passed on [TFlexCelReport.CustomizeChart](../TFlexCelReport/CustomizeChart.md)

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TCustomizeChartEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[DataFile](DataFile.md)|The file with the chart\.<br />|
|[Chart](Chart.md)|Chart that is being processed\. Modify its properties in this event\.<br />|
|[ChartName](ChartName.md)|Name of the chart\. If this is a chart sheet, then it is the name of the sheet\. Otherwise is the name of the object\.<br />|


