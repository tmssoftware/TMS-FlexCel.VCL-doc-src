---
uid: IChartFrameOptions
description: IChartFrameOptions
---

# IChartFrameOptions Interface

Description of a box, its coordinates, fill style and line style\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IChartFrameOptions = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[FillOptions](FillOptions.md)|Fill options for the frame\.<br />|
|[LineOptions](LineOptions.md)|Line options for the frame\.<br />|
|[RoundedCorners](RoundedCorners.md)|If true, the chart frame will have rounded corners\. Note that this value doesn't apply in most places\.<br />One of the only places where you can actually have rounded corners is in the frame about the chart itself\.<br />|
|[XlsxMode](XlsxMode.md)|If true, the chart was created by an xlsx\-capable Excel version \(2007 or newer\) and so has different defaults\.<br />For example, it will have different automatic colors for the series\.<br />|


