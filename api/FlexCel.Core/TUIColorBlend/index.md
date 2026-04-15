---
uid: TUIColorBlend
description: TUIColorBlend
---

# TUIColorBlend Class

Defines a complex gradient by using an array of [TUIGradientStop](../TUIGradientStop/index.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TUIColorBlend = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a color blend with n stops\.<br />|


## Methods

|Name|Description|
|---|---|
|[EnsureMinimum&#8203;AndMaximum](EnsureMinimumAndMaximum.md)|Makes sure the blend has at least 2 stops, one at position 0 and the other at position 1\.<br />|
|[InvertColorBlend](InvertColorBlend.md)|Reverts the color blend, moving the stop at position 0 to 1, the stop at 1 to 0, and mirroring all other stops in the middle\.<br />|
|[SortAscending](SortAscending.md)|Sorts the gradient stops from the lowest position to the largest\.<br />|
|[HasInterpolation&#8203;Colors](HasInterpolationColors.md)|Returns false if the gradient has only 2 colors: one at the start and one at the end\.<br />|


## Properties

|Name|Description|
|---|---|
|[Count](Count.md)|Number of gradient stops in the blend definition\.<br />|
|[Item\[const index\]](Itemconst-index.md)|Returns a particular stop in the blend\.<br />|


