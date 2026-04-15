---
uid: TXlsChartLabelPosition
description: TXlsChartLabelPosition
---

# TXlsChartLabelPosition Record

Stores a label position in the format used in xls files\. The numbers can have many different meanings depending on where they are applied\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TXlsChartLabelPosition = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[PointIs0to4000](PointIs0to4000.md)|If true, then the meaning of Point is always 0 means the left coordinate of the parent and 4000 the right\.<br />When false, the value of point is specific to the use\.<br />|
|[Point](Point.md)|Stores the position of the label, in ways specific to the label\. Is [PointIs0to4000](PointIs0to4000.md) is true, then this value is always integers between 0 and 4000\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new label position\.<br />|


