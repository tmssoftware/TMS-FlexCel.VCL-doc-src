---
uid: THSLColor.DistanceSquared
description: THSLColor.DistanceSquared
---

# THSLColor\.DistanceSquared Method

Returns the distance between 2 colors\. Not that this is not the euclidean distance, but a distance calculated to improve Hue matching\.
When converting cell colors, we try to preserve hues, so even a very pale red cell will be converted to bright red and not white or a very pale blue\.
This make it different from standard color matching as is done when adjusting images to a color palette, and where hue is not as important as here\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THSLColor/index.md">THSLColor</a>.DistanceSquared(const hue1: Double; sat1: Double; const hue2: Double; sat2: Double): Double; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**hue1**|Double||
||**sat1**|Double||
|const|**hue2**|Double||
||**sat2**|Double||


## See also

* [THSLColor](../THSLColor/index.md)

