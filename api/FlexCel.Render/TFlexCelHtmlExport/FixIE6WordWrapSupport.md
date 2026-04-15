---
uid: TFlexCelHtmlExport.FixIE6WordWrapSupport
description: TFlexCelHtmlExport.FixIE6WordWrapSupport
---

# TFlexCelHtmlExport.FixIE6WordWrapSupport Property

Some older browsers \(and Word 2007\) might not support the CSS white\-space tag\. In this case, if a line longer than a cell cannot be expanded to the right \(because there is data in the next cell\) it will wrap down instead of being cropped\. This fix will cut the text on this cell to the displayable characters\. If a letter was displayed by the half on the right, after applying this fix it will not display\.
This fix is automatically applied when [FixOutlook2007CssSupport](FixOutlook2007CssSupport.md) is selected, so there is normally no reason to apply it\. You might get  a smaller file with this fix \(if you have a lots of hidden text\), but the display will not be as accurate as when it is off, so it is reccomended to keep it off\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.FixIE6WordWrapSupport: Boolean</code></pre>

## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

