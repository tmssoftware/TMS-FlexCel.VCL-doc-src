---
uid: TFlexCelReport.GetInclude
description: TFlexCelReport.GetInclude
---

# TFlexCelReport.GetInclude Event

Fires before including a file with \<\#include>\.
Use it if you want to provide an alternative path for the file, of if you want to read the include file from a different place, for example a database or an embedded resource\.


## Remarks

If the including file is a real file \(not an stream\) and FileName is relative, it will be relative to the including file path\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.GetInclude: TGetIncludeEventHandler</code></pre>

## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

