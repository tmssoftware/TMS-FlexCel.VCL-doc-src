---
uid: IExcelGradient
description: IExcelGradient
---

# IExcelGradient Interface

Represents a gradient fill for a background cell\. This class is abstract, you need to use its children: [IExcelLinearGradient](../IExcelLinearGradient/index.md) and [IExcelRectangularGradient](../IExcelRectangularGradient/index.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IExcelGradient = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Creates a deep copy of this object\.<br />|
|[CreateStops](CreateStops.md)|Initializes the stops aray\.<br />|


## Properties

|Name|Description|
|---|---|
|[GradientType](GradientType.md)|Type of gradient stored inside this object\.<br />|
|[Stops](Stops.md)|Different colors used in the gradient\. This array must have at least one stop, and no more than 256\.<br />|


