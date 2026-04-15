---
uid: THSLColor.GetTint
description: THSLColor.GetTint
---

# THSLColor\.GetTint Method

Returns the tint needed to go from originalBrightness to newBrightness\.
A tint of 0 means no change \(OriginalBrightness == NewBrightness\), a tint of \-1 means NewBrightness = 0, and a tint of 1 means NewBrightness = 1\. So this method just does a simple interpolation to find out the needed tint\.




This method is the inverse of [ApplyTint](ApplyTint.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THSLColor/index.md">THSLColor</a>.GetTint(originalBrightness: Double; newBrightness: Double): Double; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**originalBrightness**|Double|Brightness of the original color\. \(between 0 and 1\)|
||**newBrightness**|Double|Brightness of the new color that we want to produce by applying tint to originalBrightness/>|


## Returns

The tint we need to apply to go from OriginalBrightness to NewBrigtness\.

## See also

* [THSLColor](../THSLColor/index.md)

