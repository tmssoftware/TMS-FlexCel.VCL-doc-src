---
uid: TExcelColor.RGB
description: TExcelColor.RGB
---

# TExcelColor.RGB Property

Returns the color when this structure has an RGB color, as a 0xRRGGBB integer\. This property is fully functional with Excel 2007 or newer, older versions will be converted to Indexed color before saving as xls\.




**Note:** When reading a color, the value here might not be the final one, since [Tint](Tint.md) is applied to get the final color\. Use  [ToColor\(TCoreExcelFile\)](ToColor.md#texcelcolortocolortcoreexcelfile) method to find out the RGB color stored in this struct\.


If you try to read the value of this property and [ColorType](ColorType.md) is not the right kind, an Exception will be raised\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelColor/index.md">TExcelColor</a>.RGB: Int64</code></pre>

## See also

* [TExcelColor](../TExcelColor/index.md)

