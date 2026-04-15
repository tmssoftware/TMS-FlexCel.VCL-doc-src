---
uid: TFlexCelReport.DebugIntelligentPageBreaks
description: TFlexCelReport.DebugIntelligentPageBreaks
---

# TFlexCelReport.DebugIntelligentPageBreaks Property

Set this value to true if you want to analyze how FlexCel is setting up the intelligent page breaks\. When this property is true, FlexCel will add one row at the top of the spreadsheet \(if the sheet has keeptogether column ranges\),  and one column at the left of the spreadsheet \(if the sheet has keeptogether row ranges\)\.
This row and column will show the levels of keeptogether in the respective column and row\. See ['Debugging intelligent page breaks' in the Reports Designer Guide](xref:ReportsDesignerGuide#debugging-intelligent-page-breaks) for more information\.


## Remarks

You can also set this property in the template, by writing \<\#Debug Intelligent Page Breaks> in the expressions column in the config sheet\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.DebugIntelligentPageBreaks: Boolean</code></pre>

## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

