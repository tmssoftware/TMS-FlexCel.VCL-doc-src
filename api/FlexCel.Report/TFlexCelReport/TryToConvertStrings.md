---
uid: TFlexCelReport.TryToConvertStrings
description: TFlexCelReport.TryToConvertStrings
---

# TFlexCelReport.TryToConvertStrings Property

When true, FlexCel will try to convert strings to numbers or dates before entering them into the cells\.
**USE THIS PROPERTY WITH CARE\!**  You shouldn't normally need to use this property, since FlexCel automatically enters numbers or dates in the DataSets as number or dates in the Excel file\. If you need to use this property, it means that data in your database is stored as strings when they should not be\. So the correct fix is to fix the columns you know should have numbers to have numbers, NOT to use this property\. This is just a workaround when you can't do anything else about it\.

Note also that this method is not efficient since it has to "guess" what a string might be if anything, and it might be wrong\.
Also, it might have issues with locales: Does the string "1/2/2008" means January 2 or February 1? Depends on the locale\.


## Remarks

If you have a single field which is a string but you want converted, you can write \<\#evaluate\(VALUE\(\<\#db\.StringValue>\)\)> in the cell you want converted and keep this property false\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.TryToConvertStrings: Boolean</code></pre>

## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

