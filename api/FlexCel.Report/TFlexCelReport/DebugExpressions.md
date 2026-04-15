---
uid: TFlexCelReport.DebugExpressions
description: TFlexCelReport.DebugExpressions
---

# TFlexCelReport.DebugExpressions Property

Set this value to true if you want to analyze how FlexCel is evaluating the tags in a file\. When true, a full stack trace will be written in the cell instead of the tag values\. See ['Debugging reports' in the Reports Designer Guide](xref:ReportsDesignerGuide#debugging-reports) for information on how to use those stack traces\.


## Remarks

You can also set this property in the template, by writing \<\#Debug> in the expressions column in the config sheet\.
Debug in the template will set both this property and [ErrorsInResultFile](ErrorsInResultFile.md) to true\.

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.DebugExpressions: Boolean</code></pre>

## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

