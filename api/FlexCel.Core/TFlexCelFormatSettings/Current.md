---
uid: TFlexCelFormatSettings.Current
description: TFlexCelFormatSettings.Current
---

# TFlexCelFormatSettings\.Current Method

Returns the current culture\. If you assigned a Thread Format with [SetThreadFormat](SetThreadFormat.md) then it will be returned\. If you didn't assign a Thread Format, but assigned a Global Format with [SetGlobalFormat](SetGlobalFormat.md) then the Global Format will be returned\. If you didn't assign a thread or global format, then FormatSettings will be returned\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlexCelFormatSettings/index.md">TFlexCelFormatSettings</a>.Current: <a href="../TFlexCelFormatSettings/index.md">TFlexCelFormatSettings</a>; static;</code></pre>

## See also

* [TFlexCelFormatSettings](../TFlexCelFormatSettings/index.md)

