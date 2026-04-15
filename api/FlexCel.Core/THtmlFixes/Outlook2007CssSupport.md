---
uid: THtmlFixes.Outlook2007CssSupport
description: THtmlFixes.Outlook2007CssSupport
---

# THtmlFixes.Outlook2007CssSupport Property

Outlook 2007 renders HTML worse than previous versions, since it switched to the Word 2007 rendering engine instead of Internet Explorer to show HTML emails\. If you apply this fix, some code will be added to the generated HTML file to improve the display in Outlook 2007\. Other browsers will not be affected and will still render the original file\. Turn this option on if you plan to email the generated file as an HTML email or to edit them in Word 2007\. Note that the pages will not validate with the w3c validator if this option is on\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../THtmlFixes/index.md">THtmlFixes</a>.Outlook2007CssSupport: Boolean</code></pre>

## See also

* [THtmlFixes](../THtmlFixes/index.md)

