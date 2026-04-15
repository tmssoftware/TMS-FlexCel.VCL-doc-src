---
uid: IChart3DOptions
description: IChart3DOptions
---

# IChart3DOptions Interface

Holds the 3D properties of the chart\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IChart3DOptions = interface(IInterface);</code></pre>

## Properties

|Name|Description|
|---|---|
|[XRotation](XRotation.md)|Specifies the amount a 3\-D chart shall be rotated in the X direction in degrees\. Must be between \-90 and 90\.<br />|
|[YRotation](YRotation.md)|Specifies the amount a 3\-D chart shall be rotated in the Y direction in degrees\. Must be between 0 and 360\.<br />|
|[HeightPercent](HeightPercent.md)|Height of a 3\-D chart as a percentage of the chart width\. Must be between 5%% and 500%%\.<br />|
|[DepthPercent](DepthPercent.md)|Depth of the 3\-D plot area as a percentage of its width\. Must be between 1 and 2000\.<br />|
|[Perspective](Perspective.md)|Specifies the field of view angle for the 3\-D chart in degrees\. Must be between 0 and 100\.<br />**IMPORTANT:** In Excel 2007 or newer, this value is displayed on screen in 1/2 degrees instead of degrees, so it will show as the double of the value you see here\. In Excel 2003 or older it is displayed in degrees instead\.<br />|


