---
uid: IShapeProperties.TextVerticalAlignment
description: IShapeProperties.TextVerticalAlignment
---

# IShapeProperties.TextVerticalAlignment Property

This property gets or sets the vertical alignment for the text\.


Note that xls and xlsx files behave differently when text is rotated with [TextRotated](TextRotated.md)\.
In xlsx, if you rotate the text 90 degrees clockwise, a text aligned to the top and left will be aligned to the top and right of the shape\. While in xls, the rotation is absolute and always means aligned to the top left of the shape\.


This method uses the xls way, even when dealing with xlsx files\. For more information see [Text Rotation In Xls And Xlsx](xref:TextRotationInXlsAndXlsx)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IShapeProperties/index.md">IShapeProperties</a>.TextVerticalAlignment: <a href="../TVFlxAlignment.md">TVFlxAlignment</a></code></pre>

## See also

* [IShapeProperties](../IShapeProperties/index.md)
* [TextHorizontalAlignment](TextHorizontalAlignment.md)
* [TextRotated](TextRotated.md)
* [Text Rotation In Xls And Xlsx](xref:TextRotationInXlsAndXlsx)

