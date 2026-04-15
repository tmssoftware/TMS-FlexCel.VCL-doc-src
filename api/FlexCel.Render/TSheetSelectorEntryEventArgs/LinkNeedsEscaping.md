---
uid: TSheetSelectorEntryEventArgs.LinkNeedsEscaping
description: TSheetSelectorEntryEventArgs.LinkNeedsEscaping
---

# TSheetSelectorEntryEventArgs.LinkNeedsEscaping Property

If true \(the default\) the link you provide in [Link](Link.md) is not escaped and will be escaped by FlexCel\.
So for example, the link "http://my site" will be escaped to "http://my%%20site"\.
If the link you provided was already escaped, then set this variable to false\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TSheetSelectorEntryEventArgs/index.md">TSheetSelectorEntryEventArgs</a>.LinkNeedsEscaping: Boolean</code></pre>

## See also

* [TSheetSelectorEntryEventArgs](../TSheetSelectorEntryEventArgs/index.md)

