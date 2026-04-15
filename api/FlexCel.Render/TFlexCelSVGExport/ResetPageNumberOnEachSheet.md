---
uid: TFlexCelSVGExport.ResetPageNumberOnEachSheet
description: TFlexCelSVGExport.ResetPageNumberOnEachSheet
---

# TFlexCelSVGExport.ResetPageNumberOnEachSheet Property

This property only makes sense when [AllVisibleSheets](AllVisibleSheets.md) is true\. On that case, if this property is true each sheet of the workbook will have the page number reset\. For example if the xls file has 2 sheets and each has 3 pages:  When ResetPageNumberOnEachSheet = true then footers will look like "Page 1 of 3"\. If false, they will look like "Page 5 of 6"

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelSVGExport/index.md">TFlexCelSVGExport</a>.ResetPageNumberOnEachSheet: Boolean</code></pre>

## See also

* [TFlexCelSVGExport](../TFlexCelSVGExport/index.md)

