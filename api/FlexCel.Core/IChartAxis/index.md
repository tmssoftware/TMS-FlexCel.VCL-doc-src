---
uid: IChartAxis
description: IChartAxis
---

# IChartAxis Interface

A class encapsulating the information of an axis

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IChartAxis = interface(IInterface);</code></pre>

## Properties

|Name|Description|
|---|---|
|[Index](_Index.md)|Axis Index\. 0 means primary, 1 secondary\.<br />|
|[CategoryAxis](CategoryAxis.md)|Returns information about the Category Axis \(X\-Axis on a non rotated chart\)\. Note that this might be a [TValueAxis](../TValueAxis/index.md) axis for scatter charts, or a [TCategoryAxis](../TCategoryAxis/index.md) for line or bar charts\.<br />|
|[ValueAxis](ValueAxis.md)|Returns information about the Value Axis \(Y\-Axis on a non rotated chart\)\.<br />|


