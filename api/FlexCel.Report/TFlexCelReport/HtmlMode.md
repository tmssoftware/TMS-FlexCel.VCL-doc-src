---
uid: TFlexCelReport.HtmlMode
description: TFlexCelReport.HtmlMode
---

# TFlexCelReport.HtmlMode Property

When true, FlexCel will interpret the text as HTML, and honor the tags that it can understand\.
Note that when in HtmlMode, many consecutive spaces will be interpreted as one, and carriage returns will be interpreted as spaces\. To enter real carriage returns you need to enter a
tag \(unless the text is inside \<pre> tags\)\.
Also &amp; symbols need to be escaped\. For more info on HTML syntax supported, see [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)
Note that the \<\#HTML> tag can overwrite the Html behavior on a cell by cell basis\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.HtmlMode: Boolean</code></pre>

## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

