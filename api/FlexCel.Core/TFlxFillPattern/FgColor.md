---
uid: TFlxFillPattern.FgColor
description: TFlxFillPattern.FgColor
---

# TFlxFillPattern.FgColor Field

Color for the foreground of the pattern\. It is used when the pattern is solid, but not when it is automatic\.
**Important:** This color is what you need, in the most common case where the pattern is solid\. [BgColor](BgColor.md) is ignored for solid patterns\.


This can look counterintuitive, but both FgColor and BgColor are colors for the background of the cell \(the fill pattern\)\.
To change the "foreground color" of a cell, you change the font color, not FgColor\.
So why are there 2 colors for the background? This is because Excel accepts fill patterns, where for example you might have a fill with a red background and black horizontal lines over it\.
Fot that case, BgColor would be red and FgColor will be black\.

But in the most common case, \(when [Pattern](Pattern.md) is solid\), only one color is needed, and Excel uses the FgColor in this case\.

You can think of a solid pattern as a pattern which is painted with the BgColor, and then over this it is painted with the FgColor, so BgColor is not visible\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs"><a href="../TFlxFillPattern/index.md">TFlxFillPattern</a>.FgColor: <a href="../TExcelColor/index.md">TExcelColor</a>;</code></pre>

## See also

* [TFlxFillPattern](../TFlxFillPattern/index.md)

