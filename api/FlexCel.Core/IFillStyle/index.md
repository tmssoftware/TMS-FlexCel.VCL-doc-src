---
uid: IFillStyle
description: IFillStyle
---

# IFillStyle Interface

Base definition for a Drawing fill style\. This class is abstract, and you should use its descendants like [ISolidFill](../ISolidFill/index.md) or [IGradientFill](../IGradientFill/index.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IFillStyle = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of the fill style\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is bigger than this, 0 if both objects are the same, and 1 if obj is smaller than this\.<br />|


## Properties

|Name|Description|
|---|---|
|[FillStyleType](FillStyleType.md)|Stores which kind of fill style is used\.<br />|


