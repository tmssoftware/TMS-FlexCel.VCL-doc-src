---
uid: IShapeProperties.GetAlternateText
description: IShapeProperties.GetAlternateText
---

# IShapeProperties\.GetAlternateText Method

Returns the Alternate Text for a shape\. This is used for example in the "Alt" attribute when exporting to html\.
Note that if there is no alternate text for the image \(TShapeOption\.wzDescription\), this method will return the image name\.
The idea is to return something that can describe the image for users who can't see them\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IShapeProperties/index.md">IShapeProperties</a>.GetAlternateText: string; virtual; abstract;</code></pre>

## See also

* [IShapeProperties](../IShapeProperties/index.md)

