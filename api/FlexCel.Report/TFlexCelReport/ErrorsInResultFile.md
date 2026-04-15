---
uid: TFlexCelReport.ErrorsInResultFile
description: TFlexCelReport.ErrorsInResultFile
---

# TFlexCelReport.ErrorsInResultFile Property

When true and there is an error reading cells in the template or writing the cells in the report, the error message will be written in the corresponding cell on the generated report\. No Exception will be thrown\.

You can use this property to **DEBUG** reports, as it provides an easy way to see all errors at once in the place they are produced\. But is it recommended that you leave this property **FALSE** in production,  or you could create xls files with error messages inside\. See also [DebugExpressions](DebugExpressions.md)

## Remarks

You can also set this property in the template, by writing \<\#ErrorsInResultFile> in the expressions column in the config sheet\.

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.ErrorsInResultFile: Boolean</code></pre>

## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

