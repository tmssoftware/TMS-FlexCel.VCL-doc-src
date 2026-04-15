---
uid: TSVGExportParameters.SheetPageNumber
description: TSVGExportParameters.SheetPageNumber
---

# TSVGExportParameters.SheetPageNumber Property

Page number in the sheet we are exporting\. Different from [PageNumber](PageNumber.md), this value is local to the current sheet, and it is reset every time we export a different sheet\. If you are exporting a single sheet \(FlexCelSVGExport\.AllVisibleSheets is false\), then this variable will have the same value as [PageNumber](PageNumber.md)

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TSVGExportParameters/index.md">TSVGExportParameters</a>.SheetPageNumber: Integer</code></pre>

## See also

* [TSVGExportParameters](../TSVGExportParameters/index.md)

