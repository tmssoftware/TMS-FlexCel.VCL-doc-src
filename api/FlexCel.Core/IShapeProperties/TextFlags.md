---
uid: IShapeProperties.TextFlags
description: IShapeProperties.TextFlags
---

# IShapeProperties.TextFlags Property

Option flags for the Text shape\.
**Important:**Instead of changing this flag, you should use instead [LockText](LockText.md), [TextHorizontalAlignment](TextHorizontalAlignment.md) and  [TextVerticalAlignment](TextVerticalAlignment.md)\. Changing those properties will automatically change the text flags, but in a simpler way\.


The option flags work differently in xls and xlsx files\. All properties in FlexCel assume the xls way, and convert to the corresponding properties in xlsx when saving or loading xlsx files\. For more information, check [Text Rotation In Xls And Xlsx](xref:TextRotationInXlsAndXlsx)
Mask: 0x000E Horizontal text alignment: 1 = left\-aligned 2 = centered 3 = right\-aligned 4 = justified Mask: 0x0070 Vertical text alignment: 1 = top 2 = center 3 = bottom 4 = justify Mask: 0x0200 1 if the Lock Text option is on \(Format Text Box dialog box, Protection tab\)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IShapeProperties/index.md">IShapeProperties</a>.TextFlags: Integer</code></pre>

## See also

* [IShapeProperties](../IShapeProperties/index.md)
* [TextHorizontalAlignment](TextHorizontalAlignment.md)
* [TextVerticalAlignment](TextVerticalAlignment.md)
* [LockText](LockText.md)
* [TextRotation](TextRotation.md)
* [TextRotated](TextRotated.md)
* [Text Rotation In Xls And Xlsx](xref:TextRotationInXlsAndXlsx)

