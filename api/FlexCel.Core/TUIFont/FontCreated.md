---
uid: TUIFont.FontCreated
description: TUIFont.FontCreated
---

# TUIFont.FontCreated Event

Fires after a font has been created\. You can use this event to handle fonts that don't exist in your system and are replaced by a different font by the OS\.
Note that this event is static and it applies to the whole app\.
**Remark:** As this event fires after the font has been created, it means that if you modify it the font is created twice\.
It is not going to have a big impact in performance, but if possible use the [FontCreating](FontCreating.md) event instead, as it won't cause the font to be created twice\. This event has to be used only for cases where you want to override the default operating system font substitution algorithm\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TUIFont/index.md">TUIFont</a>.FontCreated: TFontCreatedEventHandler</code></pre>

## See also

* [TUIFont](../TUIFont/index.md)

