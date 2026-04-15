---
uid: THtmlSpreadView.IgnorePrintAreas
description: THtmlSpreadView.IgnorePrintAreas
---

# THtmlSpreadView.IgnorePrintAreas Property

If true, we will use the maximum visible column and row in the spreadsheet, ignoring any print area that might be set in the sheet\. This will make the generated file look more like the interactive view in Excel, and not like what the printed page would look like\.


## Remarks

You might want to keep this property false\. Normally, if a sheet has a PrintArea set, that's because that's what you want to show to the users\. If you set this to true, you will show the full sheet\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../THtmlSpreadView/index.md">THtmlSpreadView</a>.IgnorePrintAreas: Boolean</code></pre>

## See also

* [THtmlSpreadView](../THtmlSpreadView/index.md)

