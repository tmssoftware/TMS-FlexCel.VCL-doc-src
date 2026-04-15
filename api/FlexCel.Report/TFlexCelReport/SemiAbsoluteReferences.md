---
uid: TFlexCelReport.SemiAbsoluteReferences
description: TFlexCelReport.SemiAbsoluteReferences
---

# TFlexCelReport.SemiAbsoluteReferences Property

When this property is set to true, absolute references to cells inside bands being copied will be treated as relative\.
This way, if you have "=$A$1" inside a band and cell A1 is also inside the band, it will change to A2,A3\.\.etc when the band is copied down\.
This can be useful in a master\-detail report, where you want the cells in the detail to point to a fixed cell inside every record of the master\.
See [TExcelFile.SemiAbsoluteReferences](../../FlexCel.Core/TExcelFile/SemiAbsoluteReferences.md) for more information\.


## Remarks

You can also set this property in the template, by writing \<\#Semi Absolute References> or \<\#Absolute References> in the expressions column in the config sheet\.

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.SemiAbsoluteReferences: Boolean</code></pre>

## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

