---
uid: IShapeOptionList.GetGradientStopAlpha
description: IShapeOptionList.GetGradientStopAlpha
---

# IShapeOptionList\.GetGradientStopAlpha Method

Returns a list of individual alpha values for the stops of a gradient\. This is not available in xls files, only xlsx\.
The alpha values determine the opacity of each stop, with 0 being completely transparent and 255 being completely opaque\.
This value might be null if there is no gradient in the pattern, or if the individual stops don't have a defined alpha\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IShapeOptionList/index.md">IShapeOptionList</a>.GetGradientStopAlpha: TBytes; virtual; abstract;</code></pre>

## See also

* [IShapeOptionList](../IShapeOptionList/index.md)

