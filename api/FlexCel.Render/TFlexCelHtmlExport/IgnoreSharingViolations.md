---
uid: TFlexCelHtmlExport.IgnoreSharingViolations
description: TFlexCelHtmlExport.IgnoreSharingViolations
---

# TFlexCelHtmlExport.IgnoreSharingViolations Property

When this property is true and the component tries to write any file that is locked by other thread, it will not raise an error and just assume the other thread will write the correct image\. You will normally want to have this true, so you can have many threads writing to the same file without issues\. Note that when [AllowOverwritingFiles](AllowOverwritingFiles.md) is false, this property has no effect\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.IgnoreSharingViolations: Boolean</code></pre>

## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

